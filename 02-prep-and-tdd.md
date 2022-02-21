## **First Topic**

### **ES6 Classes**

#### **Classes**
Classes are a template for creating objects. They encapsulate data with code to work on that data. Classes in JS are built on prototypes but also have some syntax and semantics that are not shared with ES5 class-like semantics.

#### **Defining classes**
Classes are in fact "special functions", and just as you can define function expressions and function declarations, the class syntax has two components: class expressions and class declarations.

## **Second Topic**

### **Using Express Routing**
Routing refers to how an application’s endpoints (URIs) respond to client requests.
<p>The following code is an example of a very basic route.<p>

<pre><code>const express = require('express')
const app = express()

// respond with "hello world" when a GET request is made to the homepage
app.get('/', (req, res) => {
  res.send('hello world')
})</pre></code>

## **Third Topic**

### **Express Routing**
#### **Overview**
Express 4.0 comes with the new Router. Router is like a mini-Express application. It doesn’t bring in views or settings but provides us with the routing APIs like .**use**, .**get**, .**param**, and **route**.

### **Basic Routes express.Router()**

<pre><code>
    // we'll create our routes here

    // get an instance of router
    var router = express.Router();

    // home page route (http://localhost:8080)
    router.get('/', function(req, res) {
        res.send('im the home page!');
    });

    // about page route (http://localhost:8080/about)
    router.get('/about', function(req, res) {
        res.send('im the about page!');
    });

    // apply the routes to our application
    app.use('/', router);
</pre></code>


1.Which 3 things had you heard about previously and now have better clarity on?
>i have heard about all of them in the prep course and have decent knowledge about them

2.Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
> classes are

3.What are you most excited about trying to implement or see how it works?
>i don't mind any of them