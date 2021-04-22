# **Modules**
Chun, Evgeny, Nafisa & Safia

---

## What are they?

---

Modules are clusters of code that are grouped based on functionality. 

Ultimately, a set of functions you want to include in your application.


---

Modules are self-contained, making them highly reusable and independent from one another.


---

To use modules, we import and export them. 
![](https://i.imgur.com/SoECoCQ.png)

---

### Additional Benefits
- easier to maintain because less code in each file
- easier to share (can use in any project)
- easier to debug

---

## What’s the difference between our own, built-in, and 3rd party modules?

---

**Own** - writing our own specific functions that we want to use in our application. We can then publish the module to npm for others to use. 

**Built-in** - core modules that come with Node installation (eg. os, http...) - these do not show in the `node_modules` folder but they exist. require is also a module!

**3rd party** - downloaded from the web via npm and copied into the `node_modules` folder.

---

**What is the package.json file for?** :8ball: 

<!-- A **package** is a file or directory that is described by a package.json file. 
 -->

A **package.json** file is a central repository of configuration for tools.

A package must contain a **package.json** file in order to be published to the npm registry. 

<!-- There are no fixed requirements of what should be in a package.json file, for an application. -->
It must respect the **JSON format**, otherwise it cannot be read by programs that try to access its properties programmatically. 

---

**Create a package.json file:** :cooking: 

Via npm run command in the terminal:
`npm init` - then running a CLI questionnaire 
           **OR**
`npm init -y` - file with default values

***

`set` default config options for the init command:
example:
        `npm set init.author.name "example_user"`
        `npm set init.license "MIT"`

---

**Default values extracted from the current directory**

`name`: the current directory name
`version`: always start at 1.0.0 (semver notation)
`description`: info from the README, or an empty string ""
`scripts`: by default creates an empty test script
`keywords`: empty
`author`: empty
`license`: ISC

`bugs`: information from the current directory, if present
`homepage`: information from the current directory, if present


---

An example ==**package.json**== file:
```javascript=
{
  "name": "node-server-intro",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1"
  }
}
```

---

**Properties breakdown** :pencil: 

`name` sets the application/package name <!-- be less than 214 characters, must not have spaces, it can only contain lowercase letters, hyphens (-) or underscores (_) - gets its own URL based on this property.-->

`version` indicates the current version (using semantic version (semver) notation - major*, minor^ , patch~)

`description` is a brief description of the app/package <!--useful if you decide to publish your package to npm so that people can find out what the package is about.-->

`main` set the entry point for the application 0

`scripts` defines a set of node scripts you can run  as command line applications. You can run them by calling `npm run XXXX`

---

`keywords` This property contains an array of keywords that associate with what your package does. <!--helps people find your package when navigating similar packages, or when browsing the https://www.npmjs.com/ website.-->

`author` Lists the package author name

`license` Indicates the license of the package.

`dependencies` sets a list of npm packages installed as dependencies

---

**Other properties:** :sparkles: 

`devDependencies` sets a list of npm packages installed as development dependencies

`engines` sets which versions of Node.js this package/app works on

`browserslist` is used to tell which browsers (and their versions) you want to support

`private` if set to true prevents the app/package to be accidentally published on npm


---

**Click here to learn more about:** :books: 

- [package.json - node.js](https://nodejs.dev/learn/the-package-json-guide)
- [package.json - npm Docs](https://docs.npmjs.com/cli/v7/configuring-npm/package-json)

<!-- package-lock.json file is to keep track of the exact version of every package that is installed so that a product is 100% reproducible in the same way even if packages are updated by their maintainers. -->
- [package-lock.json - node.js](https://nodejs.dev/learn/the-package-lock-json-file)
- [package-lock.json - npm Docs](https://docs.npmjs.com/cli/v7/configuring-npm/package-lock-json)

---

What is npm? 

NPM is the default package manager for Node.js.

---


It has two main parts:
1. An online repository where thousands of packages are hosted which are free to use and download (with npm install) - https://www.npmjs.com/

2. The CLI (Command Line Interface) this runs from a terminal and is how devs can interact with those packages  
![](https://i.imgur.com/evy514M.png)

---

Npm scripts & why they're useful

Its a default object in the package.json file and takes json key value pairs

creating custom scripts:

```
"scripts": {
"script-name" : "command to run"
}
```

 ---
 
 
Why are scripts useful:

If there's commands that you're running multiple times, storing them within the script object means that you can reference them with shorter commands that are easier to remember.

there'll be less code to write - just run npm script name.

---

It also supports some built-in scripts like test and start, which can be executed with even shorter commands.

e.g. npm t and npm run script test would do the same thing.

Npm also makes all your dependencies available to reference in the scripts so you would't need to keep using the ./node_modules/.bin/ path.

---

Some other common scripts that are usually repetitive:

Minification of Javascript/Uglification of CSS:

Linting your code

Compressing Images

Read more about here:
https://css-tricks.com/why-npm-scripts/

---

***What does npx do?***
![](https://www.freecodecamp.org/news/content/images/size/w2000/2020/01/npm-vs-npx-whats-the-difference-1024x538.jpg)

---

Sometimes you might want to take a look at a specific package and try out some commands. 

But you cannot do that without installing the dependencies in your local node_modules folder.

That’s where npx comes in.

---

***npx the package runner***

Since npm version 5.2.0 npx is pre-bundled with npm. 

npx is also a CLI tool whose purpose is to make it easy to install and manage dependencies hosted in the npm registry.

It’s now very easy to run any sort of Node.js based executable that you would normally install via npm.

---

You can run the following command to see if it is already installed for your current npm version:

`$ which npx`

If it's not, you can install it like this:

`$ npm install -g npx`

---

***These are some of the use cases that make npx extremely helpful:***

* Run a locally installed package easily

* Execute packages that are not previously installed

* Run code directly from GitHub (You can use npx to run any GitHub gists and repositories)

---

***Conclusion***

* npx helps us avoid versioning, dependency issues and installing unnecessary packages that we just want to try out.

* It also provides a clear and easy way of executing packages, commands, modules and even GitHub gists and repositories.

---

![](https://media.giphy.com/media/xUOwFSvvXbyYKzb9Ac/giphy.gif)


---

**QUIZ Time**  :question: 
Which is which? (actual JSON vs JavaScript object literal)

**Can you spot differance?**

**Option A:**
```javascript=
var person = {
  firstName: "John",
  age: 50
};
```
**Option B:**
```javascript=
{
  "name": "test-project"
}
```

---

