# React

**what  React ?**

React is a JavaScript library

## JSX

**What  JSX ?**

it is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript.

**Why JSX?**

React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called â€œcomponentsâ€ that contain both. We will come back to components in a further section, but if youâ€™re not yet comfortable putting markup in JS, this talk might convince you otherwise.

React doesnâ€™t require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.

## Updating the Rendered Element
React elements are immutable. Once you create an element, you canâ€™t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.

With our knowledge so far, the only way to update the UI is to create a new element, and pass it to root.render().

## React Only Updates Whatâ€™s Necessary

React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.
