# UX/UI

## Styled Components


---

## What is *Styled Components*?

---


- A component-driven CSS methodology
- A library for writing and managing CSS in React.


---


## CSS in JS

Styled components uses JS template literals tagged onto React components to style them:

```javascript=
// Create a Title component that'll render 
// an <h1> tag with some styles

const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: red;
`;
```

---

This Title component would be rendered in the DOM as:

```html
<h1 class="Title-xxxx xxxx">A styled Title</h1>
```

---

## Installation

Install into your project with:

```npm install styled-components```

---

## Import

Import styled components into every file that you want to use it in:

```javascript
import styled from 'styled-components'
```

---

## Create a styled component

In a React file, create a styled component like this:

```javascript=
const Button = styled.a`
  background-colour: teal;
  color: white;
  padding: 1rem 2rem;
`

const App = () => {
  return (
    <Button>
        Stylish Submit
    </Button>
  )
}

```

---

![](https://media.giphy.com/media/3o7btNa0RUYa5E7iiQ/giphy.gif)

---

## Style Inheritance 

- Styles can be inherited by other components:

```javascript=
// A new component based on Title, but with some 
// override styles

const PurpleTitle = styled(Title)`
  color: purple;
  border-color: 2px solid palevioletred;
`;

render(
  <div>
    <Title> Normal Title </Title>
    <PurpleTitle> Title but Purple </PurpleTitle>
  </div>
);
```

---

## Re-using CSS

- You can easily use duplicate styles across different HTML components too, by using the **`as`** prop.

```javascript=
render(
  <div>
    <Title>Normal Button</Title>
    <PurpleTitle>Title but Purple</PurpleTitle>
    <PurpleTitle as="a" href="/">
        I am a link but with Purple Title styles
    </PurpleTitle>
  </div>
);
```

<!-- ---

## Features

- Vendor prefixes are automatically added (improves cross-browser performance)
    - e.g. `-moz-`, `-webkit-`
    
- Unused CSS gets automatically removed :spider_web: 

- Class names are generated automatically :robot_face:  -->


---


### Styled Components x React


---


At the core of CSS is the capability to target any HTML element — globally — no matter its position in the DOM tree. 


---


But this can be cumbersome when used with components because components demand, to a certain extent, "co-location" (i.e. keeping assets such as states and styling) closer to where they’re used (known as localisation).


---

### Automatic vendor prefixing

![](https://media.giphy.com/media/l0HlFnoBUv46bp2yk/giphy.gif)


---


Automatic vendor prefixing means support for new CSS features like the all property, break properties, custom properties, and media query ranges are automatically populated to add support for older browsers.


---


![](https://i.imgur.com/voaKuIm.png)

https://github.com/postcss/autoprefixer

---

![](https://i.imgur.com/ECIpWfO.png)

---

![](https://media.giphy.com/media/3o84sq21TxDH6PyYms/giphy.gif)

---

e.g. this:

```
.App {
  display: flex;
  flex-direction: row;
  align-items: center;
}
```

---

becomes this...


```
.App {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
  -ms-flex-direction: row;
  flex-direction: row;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}
```

---

### Other features...

---

- #### Automatic critical CSS 
Styled-components keeps track of which components are rendered on a page and injects their styles and nothing else, fully automatically. Combined with code splitting, this means your users load the least amount of code necessary.

![](https://media.giphy.com/media/xT5LMGfQrJPpmXKUEM/giphy.gif)

---

- #### Easier deletion of CSS: 
It can be hard to know whether a class name is used somewhere in your codebase. styled-components makes it obvious, as every bit of styling is tied to a specific component. If the component is unused (which tooling can detect) and gets deleted, all its styles get deleted with it.

![](https://media.giphy.com/media/xULW8N9O5WD32L5052/giphy.gif)

---

- ### Simple dynamic styling
Adapting the styling of a component based on its props or a global theme is simple and intuitive without having to manually manage dozens of classes.

![](https://media.giphy.com/media/3ov9jIqqIHMEYc2LFC/giphy.gif)

---

- ### (Relatively) Painless maintenance: 
You never have to hunt across different files to find the styling affecting your component, so maintenance is "a piece of cake" no matter how big your codebase is.

![](https://media.giphy.com/media/45gODt1krqCOI/giphy.gif)

---

## Interpolation

You can pass a function ("interpolation") to a styled component's template literal to adapt it based on its props.

```jsx=
const Button = styled.button`
  background: ${props => props.sakiButton ? "green" : "white"};
  color: ${props => props.sakiButton ? "white" : "green"};
  `;
```

---

## Passed props

With a custom React component, styled-components are passed through the props.

```jsx=
const Input = styled.input`
  color: ${props => props.inputColor || "brown"};
`;
```

```jsx=
render(
  <div>
    <Input defaultValue="Michael" type="text" />
    <Input defaultValue="Jo" type="text" inputColor="electricblue" />
  </div>
);
```

---

## Attaching additional props

To avoid unnecessary wrappers that just pass on some props to the rendered component, or element, you can use the ```.attrs``` constructor. It allows you to attach additional props (or "attributes") to a component.

This way you can attach static props to an element and also attach more dynamic props to a component. The ```.attrs``` object also takes functions that receive the props that the component receives. The return value will be merged into the resulting props as well.

---

```jsx=
const Input = styled.input.attrs(props => ({
  // we can define static props
  type: "text",

  // or we can define dynamic ones
  size: props.size || "1em",
}))`
  color: palevioletred;
  font-size: 1em;
  border: 2px solid palevioletred;
  border-radius: 3px;

  /* here we use the dynamically computed prop */
  margin: ${props => props.size};
  padding: ${props => props.size};
`;

render(
  <div>
    <Input placeholder="A small text input" />
    <br />
    <Input placeholder="A bigger text input" size="2em" />
  </div>
);
```


---


### The Theme Provider


You can use the theme to provide a theme to all React componenets underneath itself. 

` import { ThemeProvider } from "styled-components";
`
In the render tree all styled-components will have access to the provided theme, even when they are multiple levels deep.



---


### Global Styles 

You can create global styles 

`import { createGlobalStyle } from "styled-components";`



---


```
const GlobalStyle = createGlobalStyle`
html{
  box-sizing: border-box;
  background: #F5F4F0;
  display:block;
  height: 100%;
  max-width: 640px;
  margin:0 auto;
  padding: 0;
}

body{
  background-color:#fafafa;
  min-height:100vh;
  padding: 1rem;
  margin-top:0;
  font-family:Verdana;
}
```



---

Then you can call it:

```
function MyApp({ Component, pageProps }) {
  return (
    <>
      <GlobalStyle />
        <Component {...pageProps} />
    </>
  );
}
```


---


# :warning: Warning! :warning: 

Define your styled components outside of the render method, otherwise it will be recreated on every single render pass.

![](https://i.imgur.com/FuHX46y.png)


---


![](https://i.imgur.com/Wl6a0Ai.png)


---


### So would we use it?

Me: Maybe but probably not
Jo: Hopefully yes
Craig: Probably not
Michael: ?


---

<!-- ---

## Useful Resources

https://styled-components.com/docs/basics#getting-started

https://www.joshwcomeau.com/css/styled-components/ -->


<!-- 
---

Bootstrap

- Written to be reusuable to make the front-end design easier
- Developed by Twitter for more consistency across their sits
- Made publicly avialable
- 10th most stared ever repo on GitHub!
- Most popular frontend library

- Install Bootstrap source files with NPM - will need a Sass compiler too. (I just cloned their starter repo which had everything in it) (or include link in head and script tags in body)
- const bootstrap = require('bootstrap') or import bootstrap from 'bootstrap' will load all of Bootstrap’s plugins onto a bootstrap object. 
- Bootstrap is mobile first (code is optimised for mobile and then scaled to bigger components with media queries. Therefore it requires the responsive viewport meta tag to be present in the `<head>`)
- has some global style settings to normalise cross browser styles. (e.g. box-sizing: border-box)
- 






---

SASS vs SCSS

-


--- -->
