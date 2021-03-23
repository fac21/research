## Advanced DOM

![](https://media.giphy.com/media/RMqUwmjPP6jeP6CeWo/giphy.gif)

Team: Amy, Evgeny, Safia & Saki

---

### What is a NodeList?


**NodeList** = a collection of nodes that can be used to access and manipulate DOM elements. 


![](https://i.imgur.com/ZGZLAAi.gif)


---

### How are they different from arrays?

**Array** = a JavaScript object which can hold more than one value at a time.

Nodelists are array-like types and so share some similarities.

---


Elements can be accessed in the same way (with a numeric index) in both and both use the same length property.

![](https://i.imgur.com/233lG7T.jpg)


---

The two are created differently: 
 - NodeLists are created by using document.querySelectorAll, childNodes, etc, other browser APIs

 - Arrays are created by either using the array literal syntax or the Array constructor

---


Other than that, NodeLists are less versatile than arrays, and we can only operate on them with these methods: 

 - item()
 - entries()
 - keys()
 - values()
 - forEach()

This isn't ideal!

---

We can convert a Nodelist to an Array by using Array.from(). 
**HOWEVER** we cannot convert an array into a NodeList!

---

## What’s the different between “live” and “static” NodeLists?
![](https://media.giphy.com/media/xUOxfejK7eCxqSB3vW/giphy.gif)

---

## Live vs. Static NodeLists

Although they are both considered NodeLists, there are 2 varieties of **NodeList**: *live* and *static*.
![](https://media.giphy.com/media/26tOYHUgZYoj2YKPe/giphy.gif)

---

### Live NodeLists

In some cases, the *NodeList* is *live*, which means that changes in the DOM automatically update the collection.

---

For example, **Node.childNodes** is *live*:
![](https://i.imgur.com/War23k8.png)

---

### Static NodeLists
![](https://media.giphy.com/media/dYsZlLg9Texw3otHKK/giphy.gif)

---

In other cases, the **NodeList** is *static*, where any changes in the DOM does not affect the content of the collection. The **document.querySelectorAll()** method returns a *static NodeList*.

---

It's good to keep this distinction in mind when you choose how to iterate over the items in the **NodeList**, and whether you should cache the list's length.

---

### What is `<template>` element?

- When you use template - the element and its contents are not rendered in the DOM, ie it will be hidden when the page loads
- But it will still hold the content, so it can still be referenced using JavaScript. 

``` html
<template id="my-paragraph">
  <p>My paragraph</p>
</template>
```

![](https://media.giphy.com/media/9GIFGeuuinRxgEj7Zq/giphy-downsized.gif)


---


- This will grab a reference to it with JavaScript and then append it to the DOM, using something like the following:

```javascript
let template = document.getElementById('my-paragraph');
let templateContent = template.content;
document.body.appendChild(templateContent);
```

---

### How is this useful?

You can use the `<template>` tag if you have some HTML code you want to use over and over again, but not until you ask for it. 

![](https://i.imgur.com/QCju3LA.jpg)


---


==`node.cloneNode(deep)`==

The **cloneNode()** method 
- creates a copy of a node, and returns the clone.
- clones all attributes and their values.
- Set the deep parameter value to true if you want to clone all descendants (children), otherwise false (shallow copy).

==`node.appendChild(node)`==

Then use the **appendChild()** or insertBefore() method to insert the cloned node to the document.


---

```javascript=
function showContent() {
  var temp = document.getElementsByTagName("template")[0];
  var clon = temp.content.cloneNode(true);
  document.body.appendChild(clon);
}
```
<!--  the HTMLTemplateElement has a content property, which is a read-only DocumentFragment containing the DOM subtree which the template represents. 
 interface represents a minimal document object that has no parent. It is used as a lightweight version of Document that stores a segment of a document structure comprised of nodes just like a standard document. The key difference is due to the fact that the document fragment isn't part of the active document tree structure. Changes made to the fragment don't affect the document (even on reflow) or incur any performance impact when changes are made.

-->

https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_template

<!-- Be careful with nested templates. They don't behave as you might expect. the outer template will not active inner templates. That is to say, nested templates require that their children also be manually activated. -->

---

Test to see if the browser supports the HTML template element by checking for the presence of the template element's content attribute.

```javascript=
function supportsTemplate() {
  return 'content' in document.createElement('template');
}

if (supportsTemplate()) {
  // Good to go!
} else {
  // Use old templating techniques or libraries.
}
```

---

Further reading:
- https://www.html5rocks.com/en/tutorials/webcomponents/template/
- https://www.html5rocks.com/en/tutorials/webcomponents/template/
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template
- https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment


---

### Thank you for listening!

![](https://media.giphy.com/media/pOA9ByTiSMrk8dV1JN/giphy.gif)

---
