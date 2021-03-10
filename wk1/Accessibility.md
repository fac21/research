# Accessibility 

---

Designing for accessibility means that more people, regardless of their physical and cognitive abilities, can access the information that your product provides.


A properly designed webpage should be easily accessible and usable by all facets of users.

---

Here is a short list of characteristics that you can design for:

---

- People who are blind/with low vision
- People with colourblindness
- Those that have physical disabilities
- Those that only use compact web-enabled devices
- Those with cognitive disorders such as ADHD
- Those speaking English as a foreign or second language

---

## Semantic HTML

---

We all know that the HyperText Markup Language (HTML) is the language of the web. It is fundamentally made up of tags that annotate and strcuture a web page. This helps both humans and machines read your content through tags.


The right HTML tags should be used for the right purposes. This is known as Semantic HTML or HTML Semantics.

---

Semantic html is an additional layer of communication. When you use semantic html you communicate more than when you use non-semantic html. Isn’t that pretty much the point of what we do? Communicate.

---

[MDN](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML) states that:

>*'A great deal of web content can be made accessible just by making sure the correct HyperText Markup Language elements are used for the correct purpose at all times'*

--- 

**_SEMANTIC HTML is important because it's:_**

---

- **Clean** — It’s easier to read and edit, which saves time and money during maintenance. 

Imagine adding the non-semantic class=”red” to a span of text. Later you decide that text should be green. That’s going to be confusing to someone editing the html at a later date.

Better would be to use something like class=”price” (assuming the content is a price on an ecommerce site). You could then change the color from red to green to blue to orange without confusing what that content is.

--- 

- **More accessible** — It can be better understood by a greater variety of devices. Those devices can then add their own style and presentation based on what’s best for the device.

A screen reader could raise and lower volume to communicate the hierarchy of your h1-h6 tags for example since you’ve clearly indicated a hierarchy.

The more meaningful the structure of your content, the better different tools can make use of your content.

---

- **Search engine friendly** — This is still debatable as search engines rank content and not code, but search engines are making greater use of things like microformats to understand content.

  + [Microformats](http://vanseodesign.com/web-design/microformats-what-how-why/)

---

## ARIA = Accessible Rich Internet Applications

Attributes that define ways to make web content and applications more accessible to people with physical and cognitive disabilities.

It is commonly used to assist other technologies when the mechanism isn't there. 

![ARIA ](ARIA.jpeg)

---

When accessibility issues cannot be managed with native HTML, ARIA can bridge the gap.

---

ARIA is not supported by all technologies so it is ALWAYS better to use native HTML where possible. This is a rule!

---

Example: widgets
Widgets supplement the HTML

Example: form hints and error messages

Example: progress bar

``` html
<div id="percent-loaded" role="progressbar" aria-valuenow="75"
aria-valuemin="0" aria-valuemax="100">
</div>

```

---


# accissibiity vs inclusive

---

 ## Accessibility 

- Using some specific features in web design to  make sure people with some type of disability will be able to use the Web.


![](https://i.imgur.com/IeUe6Q3.jpg)

---

## inclusive

- a design methodology that enables and draws on the full range of human diversity.
- Inclusive design is about designing for diversity,

![](https://i.imgur.com/NB3cuEg.jpg)


---

# Features of Accessible Websites
- Good use of HTML headings
- Accessible with keyboard
- Accessible images
- Accessible menus
- Accessible forms
- Accessible tables
- Effective use of color
- Meaningful link text
- ARIA landmark roles
- ARIA for web applications

---

### example 
- accissibiity
  using `button` tag instead of `div` tag
  
---

### inclusive
![](https://i.imgur.com/4TaWqG0.png)


- using images or diagramsinstead of large blocks of heavy text

