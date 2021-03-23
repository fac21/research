# Presentation week 3
## Checking our code

![](https://media.giphy.com/media/l4EpblDY4msVtKAOk/giphy.gif)

---

# What is static analysis?

---

Testing your code without actually running it!

---

![](https://media.giphy.com/media/toB3AnUDkqE3GENKx0/giphy.gif)

---

- Testing your code in a non-run-time environment

- Testing at the very early stage *before* running a program. 

---

This testing can be done on raw source code, without the need for deploying or building anything. 

![](https://media.giphy.com/media/w8gMxIqKe6uGrBd5fV/giphy.gif)

---

It is basically the *automated version* of a manual code review.

It's done by using tools that compare the code against sets of coding guidelines and standards. 

![](https://media.giphy.com/media/cC4jUAUPDQ91K/giphy.gif)

---

This is the opposite of **dynamic analysis** , which includes unit testing, integration testing and end-to-end testing (these find bugs *after* you've run the program)

---

If you want to know how static analysis works under the covers...

https://jotadeveloper.medium.com/abstract-syntax-trees-on-javascript-534e33361fc7

---

## How can static analysis help us?

---

![](https://i.imgur.com/X5hMLxt.png)

![](https://i.imgur.com/FNVhV0v.png)

---

![](https://i.imgur.com/areQoAR.png)

---

![](https://i.imgur.com/A0iUCmR.png)


---

## What is a linter?

A linter is a specific kind of static analysis tool that catches inconsistent formatting, stylistic errors and possible errors. 

---

## How can a linter help us avoid bugs?

---

- catches bugs that arise from syntax errors :bug: 
- gives warnings about unintuitive code
- provides suggestions for best practises :star: 
- keeps a consistent coding style
- helps make your code more readable :open_book: 
    -  less likely for other people to make errors if they use your code.

---

- Catch bugs quickly, before code even reaches the browser or a code reviewer :zap: 

![](https://media.giphy.com/media/jS2Wv3E0xSiquMLPcA/giphy.gif)

---

## How do I get a linter?

---

ESLint is the most widely used static analysis tool for JavaScript. 

It is primarily used as a linter.

![](https://i.imgur.com/viDMyVW.png)


---

ESLint has dozens of rules and you can write custom ones on top of that. 

*Example rules:*

| Always use === instead of ==
| Disallow unnecessary semicolons

---

![](https://i.imgur.com/EFWhor0.png)


Run `npm install eslint` in your terminal, in the directory that you want the linter to apply to. 

---

![](https://i.imgur.com/WsEGvjn.png)

---

- Set up a config file by running `npx eslint --init`
- Edit your `.eslintrc.{js,yml,json}` config file:

![](https://i.imgur.com/yxCo4x2.png)


---

Detailed instructions for VS Code and ES Lint are here: 

- [ESLint extension for VS Code](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Getting started with ESLint](https://eslint.org/docs/user-guide/getting-started)

---

![](https://media.giphy.com/media/TgO0Bimre5H20/giphy.gif)

---

## What is Prettier? 

<iframe src="https://giphy.com/embed/26tk0xv7qpfhjmnsY" width="480" height="362" frameBorder="0" ></iframe>

---


- An opinionated code formatter, parsing your code and re-printing it with its own rules

- Support for JavaScript, HTML, CSS, JSON, TypeScript, Markdown...

---


### Prettier V Linters: What's the difference?


<iframe src="https://giphy.com/embed/jVbSMVDoO0c6oQl3at" width="480" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

---

### Linters have two categories of rules:

- **Formatting:** e.g. max-len, no-mixed-spaces-and-tabs, keyword-spacing, comma-style.
...Prettier alleviates the need for this whole category of rules!

- **Code-quality:** e.g. no-unused-vars, no-implicit-globals, prefer-promise-reject-errors.
...Prettier doesn't help with these kind of rules!

**...Use Prettier for formatting and linters for rules to catch bugs!**

---

### A simple example using default settings...

```!=
function foo() {
    var x = 5
    var y = 6
    var z = 7
    return x + y + z
  }
```

```!=
function foo() {
  var x = 5;
  var y = 6;
  var z = 7;
  return x + y + z;
}

```

---

```!=
const name = "James";

const person ={first: name
}

console.log(person);

const sayHelloLinting = (fName) => {
console.log(`Hello linting, ${fName}`)
}

sayHelloLinting('James');
```

```!=
const name = "James";

const person = { first: name };

console.log(person);

const sayHelloLinting = (fName) => {
  console.log(`Hello linting, ${fName}`);
};

sayHelloLinting("James");

```

---

### A final example ...

```!=
foo(arg1, arg2, arg3, arg4);
```

...when format breaks down...

```!=
foo(reallyLongArg(), omgSoManyParameters(), IShouldRefactorThis(), isThereSeriouslyAnotherOne());
```

...Prettier does the work for you...
```!=
foo(
  reallyLongArg(),
  omgSoManyParameters(),
  IShouldRefactorThis(),
  isThereSeriouslyAnotherOne()
);
```


---

### Why Prettier?

<iframe src="https://giphy.com/embed/TL6poLzwbHuF2" width="480" height="354" frameBorder="0" ></iframe>

---


- Consistency - improves legibility and understanding
- Freedom - don't over think, just write code
- Inherent Learning

```!
const x = value1 && value2 || value3 && value4
```

```!
const x = (value1 && value2) || (value3 && value4);
```

---

### How to start using Prettier

<iframe src="https://giphy.com/embed/xT5LMpX3mYbYleiRsQ" width="480" height="362" frameBorder="0"></iframe>

---

**Installing Prettier**

- Install Prettier locally:
![](https://i.imgur.com/XY87yKu.png)

- Create an empty config file to let editors and other tooling know you are using Prettier:
![](https://i.imgur.com/IiN5mlz.png)

- Turn off linter rules that conflict/are unnecessary with Prettier: https://prettier.io/docs/en/integrating-with-linters.html

- Format files with Prettier:
![](https://i.imgur.com/YFxTtKd.png)

---

- Install the extension in VSCode: 'Prettier - Code Formatter'

![](https://i.imgur.com/NnUXhbU.png)

---

**Running Prettier, on demand...**
* Open Command Palette ... command + shift + P (macOS) /  ctrl + shift + P (Windows)
* Search for 'format' 
* Select 'Format Document'

![](https://i.imgur.com/3ztQn9h.png)

---

**Running Prettier, on save...**
* Open Settings menu ... command + , (macOS) / ctrl + , (Windows)
* Search for 'Editor: Format On Save'
* Ensure the option is checked

![](https://i.imgur.com/Pn6VD3r.png)


---



Nafisa/Mariya

## Pros and Cons of different tests.

![](https://media.giphy.com/media/Y4sVbn04h3dy167njC/giphy.gif)

---

 
  ![](https://media.giphy.com/media/322W3VduHG5elXisAh/giphy.gif)
_You can throw paint against the wall and eventually you might get most of the wall, but until you go up to the wall with a brush, you'll never get the corners. 🖌️_
J.B. Rainsberger

They are different tests for different use cases.

---


 **Unit Testing**
 is when you test individual functions to check if the result is what's expected.

---

Pros:
- It takes the risk out of changing older code when refactoring.


- Unit Testing helps find problems early and resolve them before further testing.

---


- Once bugs are found, it encourages devs to refactor and write better code.


- We can test parts of the project without waiting for other parts to be completed.


- Reduced cost for testing and bug-fixing.


---

Cons:

- Unit testing can't catch every error in a program. 

- Since single functions/units are being tested other integration bugs may appear

---


- You usually have to write one or more unit tests depending on how complex things are, which means more time spent on it.

- Since the tests are written by people, a developer can make a mistake that will impact the whole system.

---


## Pros and cons of Integration Testing

---

### Integration Testing verifies that several units work together in harmony.
![](https://media.giphy.com/media/jTf2Io0LtBXGZddOVE/giphy.gif)

---

### Advantages of integration testing:


---

- Provides a systematic technique for assembling a software system while conducting tests to uncover errors
![](https://media.giphy.com/media/VdzZS1qXneqUQj6YgJ/giphy.gif)
 

---

- The application is tested in order to verify that it meets the standards set by the client as well as reassuring the development team that assumptions which were made during unit testing are correct.
![](https://media.giphy.com/media/WoLmvB1Js1NrEUJNWP/giphy.gif)

---

![](https://media.giphy.com/media/0DYipdNqJ5n4GYATKL/giphy.gif)
- Integration testing can begin as soon as the relevant modules are available.

---

- Integration testing is necessary to verify whether the software modules work in unity.

---

### Disadvantages of Integration testing:

---

The Software Industry uses variety of strategies to execute Integration testing , that are :

- Big Bang Approach 

- Incremental Approach: which is further divided into following

  - Top Down Approach

  - Bottom Up Approach

  - Sandwich Approach - Combination of Top Down and Bottom Up


---


### Big Bang Approach : 
:boom:

Here **all component are integrated together at once**, and then tested.



---

### Disadvantages:
- Fault Localization is difficult.
- Some interfaces links to be tested could be missed easily.

---

- Since the integration testing can commence only after "all" the modules are designed, testing team will have less time for execution in the testing phase.
![](https://media.giphy.com/media/65ANowzpMvndyT1y3J/giphy.gif)

---

- Since all modules are tested at once, **high risk critical modules are not** isolated and tested on priority. Peripheral modules which deal with user interfaces are also not isolated and tested on priority.
![](https://media.giphy.com/media/uwlKoLulOUet2/giphy.gif)

---

### Incremental Approach:

![](https://media.giphy.com/media/pKeYeFItruwG54VzlE/giphy.gif)

---

In this approach, testing is done by **joining two or more modules that are logically related**. Then the other related modules are added and tested for the proper functioning. Process continues **until all of the modules are joined and tested successfully**.

Incremental Approach in turn is carried out by two different Methods:
- Bottom Up
- Top Down

---

In the **Bottom up strategy, each module at lower levels is tested with higher modules** until all modules are tested. 
![](https://media.giphy.com/media/DB4XwxOnpmqsoOCk4I/giphy.gif)

---

### Disadvantages of the bottom up strategy:

- **Critical modules** (at the top level of software architecture) which control the flow of application are tested **last** and may be prone to defects.

- **Early prototype is not possible.**

---

### Top down Integration:

In **Top down approach**, testing takes place **from top to down** following the control flow of the software system.
![](https://media.giphy.com/media/4ZvKhY3zjwhfakcSY7/giphy.gif)

---

Disadvantages of Top down approach:

- Needs **many** Stubs.
- Modules at **lower level** are tested **inadequately**.

---

## End-to-End Testing

---

**End-to-end tests** are tests of the **full application**. 

In an end-to-end test, you're trying to **replicate user behavior** by following user paths. 

---

![](https://media.giphy.com/media/heIX5HfWgEYlW/giphy.gif)
Some examples of this include **signing up** for an account or making a **purchase** on a site.

---

- These tests can be somewhat **expensive** to run manually, so **automating them** at least at some level can be helpful. 
- It is almost **always a good idea** to run at least a **few** end-to-end tests as they give you insight into the user experience.

E.g. A helper robot that behaves like a user to click around the app and verify that it functions correctly. Sometimes called "functional testing" or e2e.

---

### Advantages:
- replicate the user actions to complete certain tasks. Failure to run a test indicates a user workflow is interrupted which proves the value of having the test.

---

- **offer both functional and system testing**.
---

- they find lots of user impacting bugs.

---

### Disadvantages:
- **Long time to run**
    - take long to run depending on how you have written the tests. 
    - Tests checking complicated workflows take longer to run and become **difficult to troubleshoot**.

---

- These tests are **flaky**, a slight change in UI will break a test.
- **Failed tests do not pinpoint the bug** in application. More investigation is required as compared to unit tests. 

---

- **Regular maintenance** is required to run these tests.
