## **First Topic**

### **Event Loop :**
JavaScript has a runtime model based on an **event loop**, which is responsible for executing the code, collecting and processing events, and executing queued sub-tasks. This model is quite different from models in other languages like C and Java.

## **Second Topic**

### **JS callback functions :**
A callback is a function passed as an argument to another function.

## **Third Topic**

### **JS Promises :**
The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

### Promises states :
* fulfilled: Action related to the promise succeeded.
* rejected: Action related to the promise failed
* pending: Promise is still pending  not fulfilled or rejected yet.
* settled: Promise has fulfilled or rejected.

## **Fourth Topic**

## **JS Async/Await :**
### An async function is a function declared with the async keyword, and the await keyword is permitted within it. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.

* async makes a function return a Promise meaning it's written before the function and make it asynchronous function to return  a promise .

* await makes a function wait for a Promise meaning it will make the function (promise) wait after the other  lines of codes run and the stack is empty the the thing inside await will run.
  
## **Fifth Topic**

### **Test-Driven Development :**
Test-driven development (TDD) is a software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases. This is as opposed to software being developed first and test cases created later.

### TDD cycle defines:
* write a test.
* make it run.
* Change the code to make it right i.e. Refactor.
* Repeat process.
