

# CSS Architecture

What does it mean?
<!-- .element: class="fragment" data-fragment-index="0" -->

CSS's simplicity
<!-- .element: class="fragment" data-fragment-index="1" -->

---

## High-level

At a very high-level, your architecture should help you

- provide a consistent and sane environment;<!-- .element: class="fragment" data-fragment-index="0" -->
- accommodate change;<!-- .element: class="fragment" data-fragment-index="1" -->
- grow and scale your codebase;<!-- .element: class="fragment" data-fragment-index="2" -->
- promote reuse and efficiency;<!-- .element: class="fragment" data-fragment-index="3" -->
- increase productivity.<!-- .element: class="fragment" data-fragment-index="4" -->

___

---

# :)

---

## CSS Specificity 

Specificity is how browsers decide which CSS property values are the most relevant to an element and, therefore, will be applied. Specificity is based on the matching rules which are composed of different sorts of CSS selectors. 
<!-- .element: class="fragment" data-fragment-index="0" -->
**Specificity only applies when the same element is targeted by multiple declarations.**
<!-- .element: class="fragment" data-fragment-index="1" -->

---

## Selector Hierarchy

1. inline <!-- .element: class="fragment" data-fragment-index="0" -->
2. id<!-- .element: class="fragment" data-fragment-index="1" -->
3. class <!-- .element: class="fragment" data-fragment-index="2" -->
4. html tag<!-- .element: class="fragment" data-fragment-index="3" -->

---

```htmlembedded=
<style>
    #introduction{ color: red;}
    .message{ color: green;}
    h1{ color: blue;}
</style>
<h1 class="message" id="introduction">
    Hello!
</h1>

```

---

```htmlembedded=
<style>
    #introduction{ color: red;}
    .message{ color: green;}
    h1{ color: blue;}
</style>
<h1 class="message" id="introduction" style="color: pink;">
    Hello!
</h1>
```

---

**The !important exception**

```htmlembedded=
<style>
    #introduction{ color: red;}
    .message{ color: green;}
    h1{ color: blue !important;}
</style>
<h1 class="message" id="introduction" style="color: pink;">
    Hello!
</h1>
```

---

## Specificity problems


 An overly-specific selector can make your css very difficult to maintain.

---

```htmlembedded=
<style>
    #content table{ color: red;}
</style>
<section id="content">
    <table>Table 1</table>
</section>
```

---

```htmlembedded=
<style>
    #content table{ color: red;}
    .my-new-table{color:blue}
</style>
<section id="content">
    <table>Table 1 red</table>
    <table class="my-new-table">Table 2 blue</table>
</section>
```

---

```htmlembedded=
<style>
    #content table{ color: red;}
    #content .my-new-table{color:blue}
</style>
<section id="content">
    <table>Table 1 red</table>
    <table class="my-new-table">Table 2 blue</table>
</section>
```

---

If we scale this on a bigger application with different section it become very difficult and the only way to deal with it is to get progressively more specific—the notorious specificity wars we looked at above.

---

**Overly-specific selector can:**

- Limit your ability to extend and manipulate a codebase;<!-- .element: class="fragment" data-fragment-index="0" -->
- Interrupt and undo CSS’ cascading, inheriting nature;<!-- .element: class="fragment" data-fragment-index="1" -->
- Cause avoidable verbosity in your project;<!-- .element: class="fragment" data-fragment-index="2" -->
- Prevent things from working as expected when moved into different environments;<!-- .element: class="fragment" data-fragment-index="3" -->
**Lead to serious developer frustration.**<!-- .element: class="fragment" data-fragment-index="4" -->
    
---

---

One of the single, simplest tips for an easier life when writing CSS—particularly at any reasonable scale—is to keep always try and keep specificity as low as possible at all times. 


**Simple changes to the way we work, but are not limited to, can avoid a lot of specificity problems**

---

**Try to not using IDs in your CSS**

It is just not worth introducing the risk.

---

**Try to not nesting selectors** 

```css=
.content .content--paragraph .title{
    color: orange;
}
```

This type of specificity entirely avoidable—we caused this problem ourselves—we have a selector that is literally triple the specificity it needs to be. We used 300% of the specificity actually required.<!-- .element: class="fragment" data-fragment-index="0" -->
**As a rule, if a selector will work without it being nested then do not nest it.**<!-- .element: class="fragment" data-fragment-index="1" -->

---

**Solutions**
-  BEM-like Naming

```css=
.content{...}
.content--paragraph{...}
.content--paragraph-title{color: orange;}
```

---

**Try to not use ! important**

!important The word !important sends shivers down the spines of almost all front-end developers. !important is a direct manifestation of problems with specificity; it is a way of cheating your way out of specificity wars, but usually comes at a heavy price. It is often viewed as a last resort—a desperate, defeated stab at patching over the symptoms of a much bigger problem with your code.

---

- Use qualifying classes;

---

**Usefull links**

- [Specificity | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [CSS Specificity | W3schools](https://www.w3schools.com/css/css_specificity.asp)
- [CSS Specificity | cssguidelin](https://cssguidelin.es/#specificity)

---

# :)

---


# :)

---

# How can composition help us build UIs?

---

### Composition is:

"the principle that classes should achieve polymorphic behavior and code reuse by their composition (by containing instances of other classes that implement the desired functionality) rather than inheritance from a base or parent class"
<!-- .element: class="fragment" data-fragment-index="0" -->

Simply put, it's the idea that combining lots of simple independant parts gives us more flexibility in our CSS than using inheritance. 
<!-- .element: class="fragment" data-fragment-index="1" -->

---

A brief reminder what inheritance is:

This is when a child element inherits properties from the parent element: 

![](https://i.imgur.com/74ELevq.png)
<!-- .element: class="fragment" data-fragment-index="0" -->

---

Inheritance means that child elements rely on the styling of their parents and also leads to a lot of overlaying styling.

[Here is a good article](https://www.phase2technology.com/blog/used-and-abused-css) on the limitations of using inheritance.


---

Composition vs inheritance

Composition is the idea that an html component might “contain” other styles, rather than “inheriting” those styles.
<!-- .element: class="fragment" data-fragment-index="0" -->

This approach is in line with the [single-responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle) which basically says that every class has responsibility over a **single** functionality.
<!-- .element: class="fragment" data-fragment-index="1" -->


---

We can use something called *primitives* which identify and document the small layouts that we reuse.

Examples of primitives include the **stack** class that we used in our CSS workshop.
<!-- .element: class="fragment" data-fragment-index="0" -->

*"a primitive is something without its own meaning or purpose as such, but which can be used in composition to make something meaningful"*
<!-- .element: class="fragment" data-fragment-index="1" -->

Composition is essentially a combination of those primitives.
<!-- .element: class="fragment" data-fragment-index="2" -->

---

### One last thing...

Every Layout has created a bunch of [*layout primitives*](https://every-layout.dev/layouts/) which can be used. 
<!-- .element: class="fragment" data-fragment-index="0" -->

They are all **intrinsically responsive**, so in theory, don't need @media queries.
<!-- .element: class="fragment" data-fragment-index="1" -->

---

# :)

---

## CSS Naming Conventions

Organisation of code is especially important in larger and more complex projects as poorly written CSS quickly becomes more difficult to read and implement, even for the person writing it.
<!-- .element: class="fragment" data-fragment-index="1" -->

---

## BEM

BLOCK, ELEMENT & MODIFIERS
<!-- .element: class="fragment" data-fragment-index="0" -->

There are different methods in CSS code organisation, but BEM is one of the more popular approaches as it is considered less confusing.
<!-- .element: class="fragment" data-fragment-index="1" -->

---

3 levels of classes are defined in the CSS that apply a property(ies) to HTML elements.

---

# BLOCK 

A standalone element 
<!-- .element: class="fragment" data-fragment-index="0" -->

(header, container, input, menu)
<!-- .element: class="fragment" data-fragment-index="1" -->

---

# ELEMENT

Children of a BLOCK that only have meaning when tied to the BLOCK 
<!-- .element: class="fragment" data-fragment-index="0" -->

(header title, input checkbox, menu item)
<!-- .element: class="fragment" data-fragment-index="1" -->

---

# MODIFIER

A "flag" added to a BLOCK or ELEMENT that gives it a certain property 
<!-- .element: class="fragment" data-fragment-index="0" -->

(highlighted, color yellow, size medium, disabled)
<!-- .element: class="fragment" data-fragment-index="1" -->


---

<!-- .slide: data-transition="fade" -->
```css=
/* Block component */
.btn {}

/* Element that depends upon the block */ 
.btn__price {}
.btn__text

/* Modifier that changes the style of the block */
.btn--orange {} 
.btn--big {}
```
```html=
<a class="btn btn--big btn--orange" href="https://css-tricks.com">
  <span class="btn__price">$3</span>
  <span class="btn__text">BIG BUTTON</span>
</a>
```
<!-- .element: class="fragment" data-fragment-index="1" -->
![](https://i.imgur.com/Dmi78mK.png)
<!-- .element: class="fragment" data-fragment-index="2" -->

---

## Pros of BEM

- Consistently named components makes communication easier for team members working on the same project.
<!-- .element: class="fragment" data-fragment-index="0" -->
- We can easily see which modifiers and children already exist
<!-- .element: class="fragment" data-fragment-index="1" -->
- BLOCK styles are never dependant on other elements of a page so there will never be issues with inheritance
<!-- .element: class="fragment" data-fragment-index="2" -->
- BLOCKs can be reused within the same project as well as new ones
<!-- .element: class="fragment" data-fragment-index="3" -->

---

# Thanks for listening!

drinks and snacks are unfortunately not available
<!-- .element: class="fragment" data-fragment-index="0" -->
