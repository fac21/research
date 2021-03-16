# Debugging JS

![](https://media.giphy.com/media/duL28c2tptZ0zAopCf/giphy.gif)

**Team** - Chisha, Sevda , Safia & Saki

---
<!--Q ## What console methods are there other than console.log? Before I discuss that I want to make you aware that console is actually an object-->

<!--Chisha's notes: The console comes with several other useful methods that can add to a developers debugging toolkit but first we must remind ourselves, Console is an object-->

#### The Console Object
The **console object** gives you access to the browser’s (Google Chrome, Mozilla Firefox, Safari, Opera) debugging console. 

It lets you **output** strings(""), arrays[], and objects{} that help debug your code. The **console is part of the window object**, and is supplied by the Browser Object Model (**BOM**).


---


## What console methods are there other than console.log?


---

<!--Chisha notes: As mentioned before console.log is an object-->
#### ==console.log(object [, object, ...])==

There are **four** different ways of outputting a **message** to the console:

- console.==**log**==
- console.==**info**==
- console.==**warn**== - does have a **yellow background** in Chrome.
- console.==**error**== - displays both a **red background** and a **stack trace**

 ![](https://cdn-media-1.freecodecamp.org/images/DgMbvQnFNQOC7Y-1bMrzwtt9GJrXX9XQUAxy)

The most common element of the console object is ==**console.log()**==.
<!-- All four work the same way. All you do is pass one or more arguments to the selected method. It then displays a different icon to indicate its logging level. -->

 
---
  
  
**String Substitutions**
<!-- This technique uses a placeholder in a string that is replaced by the other argument(s) you pass to the method. For example: -->

**Input:** `console.log('string %s', 'substitutions')`

**Output:** `string substitutions`
 
 ![](https://cdn-media-1.freecodecamp.org/images/7e7Q5uEtCa9FDlBIV2bDnMKrgGMQzLj7MuNv)
 
**String Templates**
<!-- With the advent of ES6, template literals are an alternative to substitutions or concatenation.  -->
They use backticks instead of quotation marks, and variables go inside ==${}==:
```javascript
console.log(`bear: ${a}`);
// bear: substitutions
````

---


**Note -**  You make your console pop with different colors with string substitutions.
- You apply CSS rules in the string substitution with the ==%c== placeholder.
<!-- There are quite a few CSS properties supported by the console. -->


![](https://cdn-media-1.freecodecamp.org/images/n1PXbwS2SeGH0dXE007ItqJHQCuggJHktM4R)


---

**Console methods**

![](https://altcampus.io/_nextassets/blog/how-to-use-console-like-a-pro/console.png)
 
 
---


#### ==console.dir(object)==
The dir method displays an interactive list of the object passed to it.

`console.dir(document.body);`

![](https://cdn-media-1.freecodecamp.org/images/7H18v4UkQtV4pWkPQRd-2SZ59PAJrCJRs8wU)

<!--  Chrome displays dir differently
Ultimately, dir only saves one or two clicks. If you need to inspect an object from an API response, then displaying it in this structured way can save you some time. -->


---


#### ==console.table(object)==
The table method displays an array or object as a table.
 
 ```javascript
 const superhero = {     firstname: 'Peter',    lastname: 'Parker',}console.table(superhero);
 ```
 
 ![](https://cdn-media-1.freecodecamp.org/images/SbvV6TS9682I3VROSpaOYkGwQvAcwxLiNZJ3)


---


#### ==console.group(label)==

- made up of at least a minimum of three console calls,

<!-- and is probably the method that requires the most typing to use. But it’s also one of the most useful (especially for developers using Redux Logger). -->

A somewhat basic call looks like this:

```javascript
console.group();console.log('I will output');console.group();console.log('more indents')console.groupEnd();console.log('ohh look a bear');console.groupEnd();
```
This will output multiple levels and will display differently depending on your browser.

![](https://cdn-media-1.freecodecamp.org/images/Oh8RGjXDlufRuWiz0FWDsfRN7aTIxWcqaio3)

<!-- Each call to console.group() will start a new group, or create a new level if it’s called inside a group. Each time you call console.groupEnd() it will end the current group or level and move back up one level. -->


---

#### ==console.time([label])==
<!-- The time method, like the group method above, comes in two parts. -->

A method to start the timer (**console.time('id for timer')**) and a method to end it (**console.time('id for timer')**).

Once the timer has finished, it will **output** the **total runtime in milliseconds**,  a bit like this **timer: 0.57ms**

<!-- 
You can have up to 10,000 timers running simultaneously.
 -->

It is very useful when you need to do a quick bit of benchmarking.


---


<!-- Starts a timer with a name specified as an input parameter. Up to 10,000 simultaneous timers can run on a given page. -->

![](https://res.cloudinary.com/practicaldev/image/fetch/s--P9A9QKLN--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://cl.ly/28e1b44c3ee8/Image%25202018-09-09%2520at%252011.20.21%2520AM.png)


---


The `console.log()` method may get the job done, but    ==breakpoints== can get it done **faster.** 


--- 


With `console.log()`, you need to manually open the source code, find the relevant code, insert the console.log() statements, and then reload the page in order to see the messages in the Console. 


---
 
 
![](https://i.imgur.com/RnhQbjg.png)
 
 
---


![](https://i.imgur.com/qrhrkkK.png)


---


Now let’s replace console.log() with debugger.


---


![](https://i.imgur.com/BJ8XPPS.png)


---


![](https://i.imgur.com/Q0Nven8.png)


---


The debugger allows us to literally go into the function and see what happens step by step.


---


saki :sparkle:

will talk about debugging in the chrome tools and more about breakpoints!


---


### Using the devTools in your web broswer to debug.

![](https://i.imgur.com/AfeCU1w.png)

---

### What's in the panel?

![](https://i.imgur.com/gJ8JLwB.png)


---


### Setting breakpoints

1. Using debugger statement
2. Manually set breakpoints
![](https://i.imgur.com/6MlvIQa.png)
3. Event Listener breakpoints
![](https://i.imgur.com/eQkroBL.png)


---


### Stepping through the code

![](https://i.imgur.com/ynyfFEP.png)
- Step in the next function
- Step over next function call
![](https://i.imgur.com/8chBYuz.png)


---


#### Examine all the values of variables at that moment in time

![](https://i.imgur.com/o6wEfdM.png)


---

### Thank you for listening!
![](https://media.giphy.com/media/3osxYdXvsGw6wT5lIY/giphy.gif)

