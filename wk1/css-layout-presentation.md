# CSS Layout

---

## The Box Model

---

In CSS, everything takes up a box-like space.

<img src="https://www.sadanduseless.com/wp-content/uploads/2019/11/liquid-cats1.jpg" style="max-width: 400px;" alt="Cat in a box">

---

The box is made up of four things:

1. Content
2. Padding
3. Border
4. Margin

---

### The Box Model: 
![Box model illustration](https://every-layout.dev/images/illustrations/boxes_box-model.svg)

(You can see the box-model in action in the browser developer tools)

---

By default, the dimensions of a box are its content, with its padding and border values calculated afterwards. 

---
<img src="https://zellwk.com/images/2014/02/box-sizing.jpg" style="max-width: 450px;" alt="content-box">

If I set this element to be 100px wide, then that means the *content* is 100px.

If I add `padding: 10px` to the element's style, then the element's total width increases to `120px` (10px on the left and right). 

---

This ends up meaning that the `width` property *only describes the width of the content*.

---

This is described by the css property `box-sizing: content-box`, and it is the default value. 

---

If I change the `box-sizing` property to `border-box` in this example, the padding and content are reduced so that the entire element is 100px wide. 

<img src="https://every-layout.dev/images/illustrations/boxes_border_box.svg" style="max-width: 700px; padding: 1rem; background-color: white;" alt="box-sizing examples">

---

This is more intuitive, since the element's total box-size will be the width we actually set in the CSS. 

---

Since the `border-box` property is preferable, we can apply it to all elements in CSS using the universal selector (`*`). 

---

## How does the display property affect layout?

---

The display property controls the placement of the components of a page. The two default display values of most elements are block and inline. 

The normal flow of a page is the way block and inline elements are displayed before any changes are made to their layout. 

---

Block elements usually display one below the other as they generate line breaks before and after the element e.g. how two paragraphs would appear on a page.

This is because block elements take up the full width available.

---

Inline elements (like an anchor tag) display within a line and it will only take up the width it requires - the space between it's tags.

This is why setting a width or height on an inline element isn't possible.

---

<img src="https://media.gcflearnfree.org/content/5e82363212da9215e057b928_03_30_2020/block_vs_inline_diagram.png">


---

Some other common values of display (besides block and inline) include:

- inline-block: allows for elements to have a height and width

- flex: used for alligning items in a container

- inline-flex: allows the flex container to appear inline

- grid: establishes a grid formatting context for it's items

- none: will hide the content from all users


## How does the position property affect layout?

The `position` property can help you manipulate the location of an element. 

---

For example: sitting on top of one another, or always remaining in the same place inside the browser viewport. 

---

There are five values the position property can take:

- static
- relative
- absolute
- fixed
- sticky

---

Elements are then positioned using the `top`, `bottom`, `left`, `right`, and `z-index` properties. 

However, these properties will not work unless the `position` property is set first. 

They also work differently depending on the position value.

---

**Static**

This is the default value for elements. 

---

The element is positioned according to the normal flow of the document. The `left`, `right`, `top`, `bottom` and `z-index` properties do not affect an element with `position: static`.

![](https://i.imgur.com/9WISItE.png)

---

**Relative**

Similar to static, elements with `position: relative` remain in the normal flow of the document. 

---

But, unlike static elements, the `left`, `right`, `top`, `bottom` and `z-index` properties affect the position of the element. 

![](https://i.imgur.com/2nhIXZk.png)

---

**Absolute**

An element with `position: absolute` is positioned relative to its parent element. 

---

- The parent element must have a position value other than `position: static`. 

- If the closest parent element is not positioned, it is positioned relative to the next parent element.

---

If there's no positioned ancestor element, it is positioned relative to the <html> element.

![](https://i.imgur.com/gtMWLRq.png)

---

- No space is created for the element in the page layout: the other elements will behave as if that element is not in the document. 

- The values of `left`, `top`, `bottom`, `right`, and `z-index` determine the final position of the element.


---

**Fixed**

`position: fixed` elements are similar to absolutely positioned elements. 

They are also removed from the normal flow of the document. 

---

But unlike absolutely positioned elements, they are *always* positioned relative to the <html> element.

Fixed elements are not affected by scrolling. They always stay in the same position on the screen.

![](https://i.imgur.com/tLKjpqo.png)

---

**Sticky**

`position: sticky` is a mix of 
`position: relative` and `position: fixed`. 

---

It acts like a relatively positioned element until a certain scroll point and then it acts like a fixed element.

![](https://i.imgur.com/bwkFDJv.png)

---

![](https://i.imgur.com/lBQzxsh.gif)

---
