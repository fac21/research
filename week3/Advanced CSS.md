# Hi, I'm Advanced CSS

<img src="https://media.giphy.com/media/l0MYOowcdXdXGMWzu/giphy.gif">


## Scary, right?


---

## But once you start getting your head around it you can do some pretty cool stuff.

<img src="https://media.giphy.com/media/l0HlMlX4aKMk10hhe/giphy.gif" height=200>

## Here are some examples of things you can use to show off your skills:

---

### :nth-child selector

Instead of assigning extra classes to HTML tags you can tell a parent (or container) how you want the child elements to be styled:
<!-- .element: class="fragment" data-fragment-index="0" -->

<img src="https://i.imgur.com/QIILmTr.png" height=70>
<!-- .element: class="fragment" data-fragment-index="1" -->

```css
li:nth-child(5) {
    color: green;   
}
```
<!-- .element: class="fragment" data-fragment-index="2" -->

<img src="https://i.imgur.com/678O6F0.png" height=70>
<!-- .element: class="fragment" data-fragment-index="3" -->

```css
li:nth-child(4n-7) {
    color: green;   
}
```
<!-- .element: class="fragment" data-fragment-index="4" -->

---

### attribute selector

These can be used to target html elements that have a specified "feature". For example rather than assigning another class to your text inputs you can select them with:
<!-- .element: class="fragment" data-fragment-index="0" -->

```css
input[type="text"] {
  width: 200px;
  }
```
<!-- .element: class="fragment" data-fragment-index="1" -->

Or even go as complex as to change the styling of each link whose href attribute is a jpg file:
<!-- .element: class="fragment" data-fragment-index="2" -->

```css
a[href$=".jpg"] {
  background: url(jpeg.gif) no-repeat left 50%;
  padding: 2px 0 2px 20px;
  }
```
<!-- .element: class="fragment" data-fragment-index="3" -->

---

![](https://media.giphy.com/media/9V1F9o1pBjsxFzHzBr/giphy.gif)

---

---

# Sevda

## What are “combinator” selectors? Can you provide examples where they’re useful?

---

A combinator is a way to define the relation between selectors. 

---

**There are 4 types of combinators as:**

---

==_Descendant Selector (space)_==
A descendant selector targets all elements of a kind under a specified parent element.

---

>  <img src="https://i.imgur.com/IIKP2Bp.png" alt="" width="300"/>
 
<img src="https://i.imgur.com/KBlDmJi.jpg" alt="" width="500"/>

---

==_Child Selector (>)_==
Child selectors target elements directly under a parent element.

---

<img src="![](https://i.imgur.com/5hxaKcz.png)" alt="" width="300px"/>

<img src="https://i.imgur.com/pvWn6ZG.png" alt="" width="500px"/>

---

==_Adjacent Sibling Selector (+)_==
Adjacent means **“immediately following”** and in CSS it is represented with the plus operator.

---

> <img src="https://i.imgur.com/AnBeRQh.png" alt="" width="300px"/>
<img src="https://i.imgur.com/n9TFuAo.jpg" alt="" width="500px"/>

---

==_General Sibling Selector (~)_==
Sibling means elements on the same level, so none of them are their parent or children.

---

> <img src="https://i.imgur.com/gMqkQBg.png" alt="" width="300px"/>
<img src="https://i.imgur.com/2Xl68kX.jpg" alt="" width="500px"/>

---

Say, in real life we had a set of radio buttons!

---

<img src="https://i.imgur.com/7l1Cbwc.png" alt="" width="400px"/>

---

The general sibling selector can be used to style the text in the label after the radio button when an option is checked.

<img src="https://i.imgur.com/V5WwftD.png" alt="" width="300px"/>

---

# Rosie

## What are pseudo-elements? Can you provide examples where they’re useful?

---

### What are psuedo elements?

Keywords added to a selector that let you style a specific part of the selected element(s). For example,

p::first-word {
color: blue
}

<span style="color:blue">Can</span> be used to change the font of the first line of a paragraph.

---

### But it gets cooler than that!


### ::before

### ::after

*For every element on the page, you get two more free ones that you can do just about anything another HTML element could do*

So what can we use this for?

--- 

![](https://i.imgur.com/nRcnSkv.png)


---

![](https://i.imgur.com/u4ol0OM.png)

---

![](https://i.imgur.com/CusewCh.png)

---

![](https://i.imgur.com/dWO7wfa.png)

---


By adding 

position: absolute 

to the styling of our before / after pseudo elements, we can layer them on top of each other.

--- 


---

## How might you create custom-styled checkboxes using the combinator and pseudo elements?

Let's run through how you could create a custom-styled checkbox using the combinator and pseudo elements...

---

### ¿Which CSS Selectors could we use?

– Type selector `type` - selects all elements of the given `type` (e.g. `input` will select all `<input ... />` nodes)

– Attribute selector `[attribute="value"]` - selects an element with `attribute` where its value is exactly `value`

– Psuedo-class `:checked` - selects checkbox/radio input types or `option`s in a `select` that are selected/checked/on/active

– Psuedo-element `::before` - styleable element that doesn't actually exist in the DOM; considered the first child of the selected element

---

### Continued....

– Universal selector `*` - selects anything/everything

– Child combinator `>` - combines two selectors; narrowing the selection on the right-hand side to only those elements that are direct descendants of elements selected by the left-hand side.

– Adjacent sibling combinator `+` - combines two selectors; narrowing the selection on the right-hand side to only those elements that are the siblings immediately after the elements on the left-hand side

---
## ¡Importante CSS styles!

– `content` - used in the `::before` psuedo-element to set its content

– `display` - specifically `none` to hide elements and `inline-block` to make our otherwise inline checkbox able to have a consistent width and height

– `width / height` - does what you think: sets width and height of the element

– `color` - sets the color of the text

– `text-align` / `vertical-align` - used for adjusting the position of our check/checkbox to its label

– `border` styles - How we'll form and color the checkbox

– `background` - sets the background color (used to fill in the checkbox when it is checked)

---

### Let's go deeper...

![](https://media.giphy.com/media/swtiK9jRfE0zS/giphy.gif)

---

### Checkbox example:

https://codepen.io/mikailbadoula/pen/GRrRbVa

---

How it works: 

– Hide the actual checkbox input
– Show a styled element that looks like an empty checkbox when the input is unchecked
– Show a styled element that looks like a checked checkbox when the input is checked

---

#### Checkbox HTML:
```
<label>
  <input type="checkbox" name="key" value="value" />
  <span>I am a checkbox</span>
</label>
```

##### CSS – hide the unstyleable checkbox:
```
label > input[type="checkbox"] {
  display: none;
}

```
---

#### CSS - make our own checkbox

Building from the selection in the previous section; we add ``+ *`` to select any element as long as it is the direct subsequent sibling to the checkbox of interest and then ``::before`` to select the said psuedo-element for making the box.

```
label > input[type="checkbox"] + *::before {
  content: "";
  display: inline-block;
  vertical-align: bottom;
  width: 1rem;
  height: 1rem;
  border-radius: 10%;
  border-style: solid;
  border-width: 0.1rem;
  border-color: gray;
}
```

---

### CSS – make Checkbox change when checked

The important part here being `:checked` is placed after the input[type="checkbox"] (since that is the element that is checked or not). The `content:` is set to the '✓' emoji,

```
label > input[type="checkbox"]:checked + *::before {
  content: "✓";
  color: white;
  text-align: center;
  background: teal;
  border-color: teal;
}
label > input[type="checkbox"]:checked + * {
  color: teal;
}
```
---

## *Fin*

---
