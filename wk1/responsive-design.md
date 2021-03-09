
## How do you design and build a webpage that looks good on any device?
![](https://media.giphy.com/media/13FrpeVH09Zrb2/giphy.gif)

By Evgeny, Mariya, Neville & Safia

---

## What are absolute and relative units?
![](https://media.giphy.com/media/4JVTF9zR9BicshFAb7/giphy.gif)

---

### Relative length units
Specify a length relative to another length.

- Font-relative Lengths
- Viewport-percentage lengths

---

**Font-relative Lengths**

Refer to the font metrics of the element on which they are used—or, in the case of rem, the metrics of the root element).

- **em** - font size of the element **M**

- **rem** - font size of the **root** element

![Ex & ch](https://every-layout.dev/images/illustrations/units_ch-ex.svg)


---

**Viewport-percentage lengths**

Are relative to the size of the initial containing block 

When the height or width of the initial containing block is changed, they are scaled accordingly. 

- **vw** - 1% of viewport’s width
- **vh** - 1% of viewport’s height
- **vmin** - 1% of viewport’s smaller dimension
- **vmax** - 1% of viewport’s larger dimension

---

### Absolute length units
Are fixed in relation to each other and anchored to some physical measurement.

- **px** - pixels
- **in**- 1in == 96px 
- **cm**- 1cm == 37.8px
- **mm** - 1mm == 0.1cm == 3.78px
- **pt** - point - 1pt == 1/72 of an inch
- **pc** - picas - 1pc == 12pt.

Not technically a length..
- **%** - percentage -  The percentage is always looking at the size of its parent. 

---

### What CSS units should we use for dimensions?
![](https://media.giphy.com/media/jpFGZoB6VzEJ9HXuLy/giphy.gif)

As a rule of thumb, 
 - em units are better for sizing inline elements, SVG icons
 - rem units are better for block elements
 
 ---
 ```
1em == 16px == 0.17in == 12pt == 1pc == 4.2mm == 0.42cm
```
 
 Recommendations of unit types per media type:

Media | Recommended | Occasional use | Infrequent use | Not recommended
:--- | :--- | :--- | :--- | :---
Screen | em, rem, % | px | ch, ex, vw, vh, vmin, vmax | cm, mm, in, pt, pc
Print | em, rem, % | cm, mm, in, pt, pc | ch, ex | px, vw, vh, vmin, vmax

---


### What are Media Queries?

![](https://media.giphy.com/media/iB4PoTVka0Xnul7UaC/giphy.gif)

Media Queries are a way to *only* apply CSS when the browser and device environment matches a rule that you specify.

---

### When should you use Media Queries?

<br>

They are a key part of responsive web design, allowing you to create different layouts depending on the size of the viewport

<br>

```
        @media only screen and (min-width: 600px) {
          body {
            background-color: lightblue;
          }
        }
        
```

---

### Are Media Queries only for screen size?

<br>

Media Queries can also be used to detect and respond to other features about the environment your site is running on. For example:

<br>

- Width and height of the viewport or device
- Orientation of device
- Resolution
- Pointing device - touch screen/mouse

---

### Media Queries: Syntax

<br>

- A media type: screen, print, speech, all;
- A media expression: a rule, or test, to be applied to a specified feature;
- CSS code: only if correct media type and test passes

<br>
<br>

```
        @media mediatype and (expression) {
          CSS code;
        }
```

---


### Media Queries: By example...

<br>

```
        @media print {
            body {
                font-size: 12pt;
            }
        }
```

<br>

```
        @media (orientation: landscape) {
            body {
                color: rebeccapurple;
            }
        }
```

---


### Media Queries: By example...

<br>

```
        @media screen and (min-width: 40em) {
            article {
                display: grid;
                grid-template-columns: 3fr 1fr;
                column-gap: 20px;
            }
            nav ul {
                display: flex;
            }
            nav li {
                flex: 1;
            }
        }
```


---

## How can mobile-first CSS make responsive styling easier?

![](https://media.giphy.com/media/3ohhwfsweRaKsZo17W/giphy.gif)

---

## Always Design for Mobile First

![](https://i.imgur.com/WD9mFRA.png)

* “Mobile first” means to create your content first on the smallest devices that the users are likely to have, such as phones or tablets and then for a desktop device. 

---

* Advanced styles for larger screens are then added into the stylesheet via media queries. This approach uses ``min-width`` media queries.

Here’s a quick example:

---

```css

// This applies from 0px to 600px
body {
  background: red;
}

// This applies from 600px onwards
@media (min-width: 600px) {
  body {
    background: green;
  }
}
```
`<body>` will have a red background below 600px. Its background changes to green at 600px and beyond.

---

### 4 ways Mobile First makes styling easier:
![](https://media.giphy.com/media/MAdTaVHfXiyZgXCqTk/giphy.gif)

---

#### 1. Since mobile devices are smaller, you will think about what is really necessary to display, the useful main content that someone needs to know. 

#### 2. If you design your content to be mobile first, then your code will be simpler and you won’t have to do a lot to get it looking good on a phone. 

---

#### 3. Since phones have smaller processors, the device does not have to run through a lot of code and then adjust to a mobile device, removing the CSS that is not needed.

#### That leads to the conclusion that desktop-first can lead to redundant code

---

```javascript
.section {                        
  display: flex;
  justify-content: space-between;
}
.columns {
  width: 30%;
}
@media (max-width: 600px) {
  .section {
    display: block;
  }
  .columns {
    width: 100%;
  }
}
```
##### So, why do we need to first declare a display: flex only to put it back to the default display: block in the media query for mobile. And also, for columns sometime, we make the width smaller and then, once again, go back to the default 100% for mobile later on.

---

The mobile-first approach has a lot less redundant code. Because if there is no styling of the text or background colors, there is no styling, except for what we need in the media queries!

---

#### 4. Mobile traffic is growing. . . fast
According to [oberlo.co.uk](https://www.oberlo.co.uk/statistics/mobile-internet-traffic) the number of website visits coming from mobile devices already surpasses desktop visits. As of February 2021, 55.56 percent of all web traffic comes through mobile phones. So, as mobile viewership is growing and so is the demand for mobile-friendly websites, I think it is worth to create our websites for mobile first.

---

#### And if you ask again the question: 
Why mobile-first is easier? 
I can simply say:
#### Websites are naturally responsive before we even write a single line of CSS.

If you remove the CSS from any page on the internet, even some site made in for a very specific screen size back in 2001, you will still have a responsive, mobile-friendly website!






