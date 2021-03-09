# Accessibility 

---

## Semantic HTML

---

When writing markup, it has to be as accessible to as many people as possible. These are the main groups to reach that are commonly left behind:

---

1) People who are blind/with low vision
2) People with colourblindness
3) Those that have physical disabilities
4) Those that only use compact web-enabled devices
5) Those with cognitive disorders such as ADHD
6) Those speaking English as a foreign or second language

---

It is important that we are always designing for accessibility so more people can access the information our product provides. Semantic HTML can help us reach many more people because of its nature. 

---

Semantic HTML benefits many of the groups mentioned as it is always chosen based on importance of structure of content. Semantic HTML is about the importance of hierarchy in writing text. This helps both humans and machines read your content. 

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

