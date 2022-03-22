### How it works
The bidirectional channel between the Socket.IO server (Node.js) and the Socket.IO client (browser, Node.js, or another programming language) is established with a WebSocket connection whenever possible, and will use HTTP long-polling as fallback.

The Socket.IO codebase is split into two distinct layers:

the low-level plumbing: what we call Engine.IO, the engine inside Socket.IO
the high-level API: Socket.IO itself
Engine.IO
Engine.IO is responsible for establishing the low-level connection between the server and the client. It handles:

the various transports and the upgrade mechanism
the disconnection detection
The source code can be found here:

server: https://github.com/socketio/engine.io
client: https://github.com/socketio/engine.io-client
parser: https://github.com/socketio/engine.io-parser
protocol description: https://github.com/socketio/engine.io-protocol
Transports
There are currently two implemented transports:

HTTP long-polling
WebSocket
HTTP long-polling
The HTTP long-polling transport (also simply referred as "polling") consists of successive HTTP requests:

long-running GET requests, for receiving data from the server
short-running POST requests, for sending data to the server
Due to the nature of the transport, successive emits may be concatenated and sent within the same HTTP request.

WebSocket
The WebSocket transport consists, well, of a WebSocket connection, which provides a bidirectional and low-latency communication channel between the server and the client.

Due to the nature of the transport, each emit is sent in its own WebSocket frame (some emits may even result in two distinct WebSocket frames, more information here).

Handshake
At the beginning of the Engine.IO connection, the server sends some information:

{
  "sid": "FSDjX-WRwSA4zTZMALqx",
  "upgrades": ["websocket"],
  "pingInterval": 25000,
  "pingTimeout": 20000
}
the sid is the ID of the session, it must be included in the sid query parameter in all subsequent HTTP requests
the upgrades array contains the list of all "better" transports that are supported by the server
the pingInterval and pingTimeout values are used in the heartbeat mechanism
Upgrade mechanism
By default, the client establishes the connection with the HTTP long-polling transport.

But, why?

While WebSocket is clearly the best way to establish a bidirectional communication, experience has shown that it is not always possible to establish a WebSocket connection, due to corporate proxies, personal firewall, antivirus software...

From the user perspective, an unsuccessful WebSocket connection can translate in up to at least 10 seconds of waiting for the realtime application to begin exchanging data. This perceptively hurts user experience.

To summarize, Engine.IO focuses on reliability and user experience first, marginal potential UX improvements and increased server performance second.

To upgrade, the client will:

ensure its outgoing buffer is empty
put the current transport in read-only mode
try to establish a connection with the other transport
if successful, close the first transport
You can check in the Network Monitor of your browser:

Successful upgrade

handshake (contains the session ID — here, zBjrh...AAAK — that is used in subsequent requests)
send data (HTTP long-polling)
receive data (HTTP long-polling)
upgrade (WebSocket)
receive data (HTTP long-polling, closed once the WebSocket connection in 4. is successfully established)
Disconnection detection
The Engine.IO connection is considered as closed when:

one HTTP request (either GET or POST) fails (for example, when the server is shutdown)
the WebSocket connection is closed (for example, when the user closes the tab in its browser)
socket.disconnect() is called on the server-side or on the client-side
There is also a heartbeat mechanism which checks that the connection between the server and the client is still up and running:

At a given interval (the pingInterval value sent in the handshake) the server sends a PING packet and the client has a few seconds (the pingTimeout value) to send a PONG packet back. If the server does not receive a PONG packet back, it will consider that the connection is closed. Conversely, if the client does not receive a PING packet within pingInterval + pingTimeout, it will consider that the connection is closed.

The disconnection reasons are listed here (server-side) and here (client-side).

Socket.IO
Socket.IO provides some additional features over the Engine.IO connection:

automatic reconnection
packet buffering
acknowledgments
broadcasting to all clients or to a subset of clients (what we call "Room")
multiplexing (what we call "Namespace")
