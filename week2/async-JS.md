---

slideOptions:
  transition: 'slide'
  transition-speed: fast
  progress: false
  spotlight:
    enabled: false

---

## Asynchronous JavaScript

![](https://giphy.com/embed/TQmOxn9y3BoFG)

- Synchronous' and Asynchronous code, Blocking

- Callbacks and Promises

- Event Loop and Call Stack

---


## Synchronous Programming


![](https://giphy.com/embed/kI4NJZ2T7HO5Y6aecx)

In a synchronous programming model
things happen one at a time, in the order they appear

---

![](https://giphy.com/embed/hSulTsYX8yatJMVtiQ)

- JavaScript is a single threaded language

- While each operation is being processed, nothing else can happen.<!-- .element: class="fragment" data-fragment-index="0" -->

---

A Simple Example...

<br>

``` = !
const btn = document.querySelector('button');

btn.addEventListener('click', () => {
  alert('You clicked me!');

  let paragraph = document.createElement('p');
  paragraph.textContent = 'This is a newly-added paragraph.';
  document.body.appendChild(paragraph);
});
```

---

## Blocking

![](https://giphy.com/embed/PfR64JndE2DhS)

---

- When calling a function that performs a long-running action, it only returns when the action has finished.


- This stops the rest of your program for the time the function takes<!-- .element: class="fragment" data-fragment-index="0" -->

- From the perspective of the user, the entire program stops<!-- .element: class="fragment" data-fragment-index="1" -->

---

An example ...

![](https://giphy.com/embed/lfJDAwGrqPuKY)


``` !=
const fs = require('fs');
const data = fs.readFileSync('/file.md'); 

// blocks here until file is read

console.log(data);
moreWork(); // will run after console.log
```

---

## Asynchronous Programming

![](https://giphy.com/embed/wN4GIuq6mjMGzMuhxf)


![](https://giphy.com/embed/JSnKGLvrFvYU8)


**An asynchronous programming model allows multiple things to happen at the same time.**

---

![](https://giphy.com/embed/l1Etf7wwmO3eigKzK)


- JS is not an asynch language, BUT it can be manipulated to work in an asynchronous way

- The program doesn't wait for one action to complete, and can move on to the next task<!-- .element: class="fragment" data-fragment-index="0" -->

- When the previous action finishes, the program is informed and gets access to the result<!-- .element: class="fragment" data-fragment-index="1" -->

- Many Web API features now use asynchronous code to run. <!-- .element: class="fragment" data-fragment-index="2" -->

---
![](https://giphy.com/embed/H46Dtwtwo1FDO)

There are two main types of asynchronous code used in JavaScript:
- Old-style Callbacks<!-- .element: class="fragment" data-fragment-index="0" -->
- Newer-stlye Promises<!-- .element: class="fragment" data-fragment-index="0" -->

---

# Tiarama
![](https://media.giphy.com/media/pWLSXjkAv1c1gwCB4E/giphy.gif)

---

### What are Asynchronous Callbacks?  <img src="https://media.giphy.com/media/rmnJgFO2XdPG0/giphy.gif" style="height: 180px;"><!-- .element: class="fragment" data-fragment-index="0" -->

Functions that are specified as **arguments when calling another function**.<!-- .element: class="fragment" data-fragment-index="1" --> 

When the code has finished running it **calls the callback function**.<!-- .element: class="fragment" data-fragment-index="2" --> 
It can be used to let you know that the function is finished, or something of interest has happened.

---

## Here's an Example: <img src="https://media.giphy.com/media/26DN7IkiNlMgmKiKA/giphy.gif" style="height: 180px;"><!-- .element: class="fragment" data-fragment-index="1" -->

```javascript
btn.addEventListener('click', () => {
  alert('You clicked me!');
```
<!-- .element: class="fragment" data-fragment-index="2" -->
The first parameter is the type of event to be listened for, and the second parameter is a callback function that is **invoked when the event is fired**.<!-- .element: class="fragment" data-fragment-index="3" -->

---

When we pass a callback function as an argument to another function, we are only passing the function's **reference** as an argument. i.e, the callback function is not executed immediately.<img src="https://media.giphy.com/media/eiBKBoOXb0U1i/giphy.gif" style="height: 120px;">

It is “called back” (hence the name) **asynchronously** somewhere inside the containing function’s body.<!-- .element: class="fragment" data-fragment-index="2" -->

The **containing function** is responsible for executing the callback function when the time comes.<!-- .element: class="fragment" data-fragment-index="3" -->

---

Note that not all callbacks are async — some run synchronously. An example <img src="https://media.giphy.com/media/26DN7IkiNlMgmKiKA/giphy.gif" style="height: 50px;"> is when we use Array.prototype.forEach() to loop through the items in an array<!-- .element: class="fragment" data-fragment-index="0" -->

```javascript
const gods = ['Apollo', 'Artemis', 'Ares', 'Zeus'];

gods.forEach(function (eachName, index){
  console.log(index + '. ' + eachName);
});
```
<!-- .element: class="fragment" data-fragment-index="1" -->
In this example we loop through an array of Greek gods and print the index numbers and values to the console.<!-- .element: class="fragment" data-fragment-index="2" -->

---

The expected parameter of forEach() is a callback function, which itself takes two parameters, a reference to the array name and index values.<!-- .element: class="fragment" data-fragment-index="0" --> 
However, it doesn't wait for anything — it runs immediately.<!-- .element: class="fragment" data-fragment-index="1" -->
<img src="https://media.giphy.com/media/WqRk3K1jpyadXWGmHm/giphy.gif" style="height: 350px;"><!-- .element: class="fragment" data-fragment-index="2" -->

---

# Pros
<img src="https://media.giphy.com/media/ugOaZ3Wi8lqZW/giphy.gif" style="height: 400px;">

---

- Callbacks are versatile — not only do they allow you to control the order in which functions are run and what data is passed between them, they also allow you to pass data to different functions depending on circumstance.<!-- .element: class="fragment" data-fragment-index="0" -->

- Notifications may occur more than once (and thus need to call the callback more than once). Promises are one-shot devices and cannot be used for repeat notifications.<!-- .element: class="fragment" data-fragment-index="1" -->

---

# Cons
<img src="https://media.giphy.com/media/kaTAaINpx0KKmAYd8o/giphy.gif" style="height: 400px;">

---

Using callbacks is slightly old-fashioned now, but you'll still see them in use in a number of older APIs.

Call backs are less readable as the errors are not implicitly defined.

"callback hell" 

<img src="https://media.giphy.com/media/2dozqvgZCKKPPY3LDN/giphy.gif" style="height: 200px;">

---

![](https://res.cloudinary.com/practicaldev/image/fetch/s--1ppnEIAU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/a79vj0fvvdylajtcqz87.gif)

---

# Jo

## How do promises help us? 

---

Promises allow us to defer later actions until a previous action has completed, or allow us to respond to its failure.

---

Using promises is the more modern way to write async code.

(e.g. `fetch()` is a relatively recent addition to Javascript)

---

"I promise to tell you if the code was completed successfully or not"

![](https://media.giphy.com/media/l2JdUhw8mMsaQxaAE/giphy.gif)

---

It allows async methods to work more like syncronous methods - i.e., they can return values. 

However, instead of immediately returning the final value, the async method returns a *promise* to supply the value at some point in the future.

![](https://media.giphy.com/media/dw2yCF4MhcNmSMgpfe/giphy.gif)

---

You can attach callback functions directly to the promise object, rather than having to pass callbacks to a function. 

---

Promises help avoid "callback hell" - a nested mess of callbacks within callbacks. 

___

This is possible because multiple async operations can be chained together with `.then()`.

![](https://media.giphy.com/media/9D7emqug6RP3YB7oNf/giphy.gif)

---

### Other advantages of Promises

---


* Always called in the order they are placed in the event queue

![](https://media.giphy.com/media/xT5LMuHy92KbOfnd8A/giphy.gif)


---

* The code appears as though it is executing in a top-down way (more readable)

---

* errors handled by a single `.catch()` block

![](https://media.giphy.com/media/13ywPzPJdfhmBG/giphy.gif)

---

- Don't lose control of how the functions will be executed

![](https://www.thetimes.co.uk/imageserver/image/%2Fmethode%2Ftimes%2Fprod%2Fweb%2Fbin%2F1f5a058c-caa8-11e9-b1f3-b9799171edee.jpg?crop=1500%2C1000%2C0%2C0)

---

### Summary: 

Promises are a way to write code asyncronously, and help to fix callback hell!

![](https://media.giphy.com/media/vlWWl1T5Dwuac/giphy.gif)


---

### More reading: 

- See [callbackhell.com](http://callbackhell.com/)

---

<style>
    th, td { 
      font-size: 20px;
      border-collapse: collapse;
      border-width:3px
    }
    </style>

### Callbacks vs Promises



|  | Callbacks | Promises |  |
| -------- | -------- | -------- | -------- |
| <img src="https://media.giphy.com/media/ugOaZ3Wi8lqZW/giphy.gif" style="height: 100px;">    | Control the order functions are run    | Always called in the order they are placed in the event queue    | <img src="https://media.giphy.com/media/kaTAaINpx0KKmAYd8o/giphy.gif" style="height: 100px;">
| <img src="https://media.giphy.com/media/ugOaZ3Wi8lqZW/giphy.gif" style="height: 100px;"> | Notifications can be run more than once | One shot, cannot be used for repeat notifications | <img src="https://media.giphy.com/media/kaTAaINpx0KKmAYd8o/giphy.gif" style="height: 100px;"> |
| <img src="https://media.giphy.com/media/kaTAaINpx0KKmAYd8o/giphy.gif" style="height: 100px;"> | "Callback Hell" | All errors handled by a single `.catch()` block | <img src="https://media.giphy.com/media/ugOaZ3Wi8lqZW/giphy.gif" style="height: 100px;">|
| <img src="https://media.giphy.com/media/kaTAaINpx0KKmAYd8o/giphy.gif" style="height: 100px;"> | Outdated | Don't lose control of how the functions will be executed | <img src="https://media.giphy.com/media/ugOaZ3Wi8lqZW/giphy.gif" style="height: 100px;">|


---

# Event Loop & Call Stack

---

![](https://i.imgur.com/WzCMcra.png)


---


### When do we make use of the event loop?
<!-- .element: class="fragment" data-fragment-index="0" -->
- Executing code after other functions are done executing<!-- .element: class="fragment" data-fragment-index="1" -->
- Heavy computation that is not required to run sequentially (stop blocking)<!-- .element: class="fragment" data-fragment-index="2" -->

---

ES6 introduced the concept of the **Job Queue**, which is used by Promises (also introduced in ES6). 

It's a way to execute the result of an async function as soon as possible, rather than being put at the end of the call stack.


---

Are these messages being printed in the correct order? 

![](https://i.imgur.com/ZD8uPS4.jpg)

---

Correct order:
<br>

```
// Message no. 1: Sync
// Message no. 5: Sync
// Message no. 3: 1st Promise
// Message no. 4: 2nd Promise
// Message no. 2: setTimeout
```
<!-- .element: class="fragment" data-fragment-index="0" -->

<br>

Promises get called before setTimeout!
<!-- .element: class="fragment" data-fragment-index="1" -->

