# Deployment
## How can we deploy our Node server to a cloud provider like Heroku? 

---

## What is Heroku? 
Jo

---

![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftucu.ca%2Fwp-content%2Fuploads%2F2018%2F10%2Fserver-farm.jpg&f=1&nofb=1)

---

A cloud-based *Platform as a Service* (PaaS). :cloud: 

---

![](https://media.giphy.com/media/xT0xeuOy2Fcl9vDGiA/giphy.gif)

---

A set of cloud-based computing services for running apps and computer program bundles:

- Networks
- Servers
- Operating system
- Middleware
- Database
- Testing
- Application design
- Security

---

:question: What is an application?

---

A collection of source code, maybe a framework, and some build instructions that describe any dependencies. 

---

Heroku lets you deploy, run and manage applications. 

*"Easily deploy an app, change its configuration, view logs, scale, and attach add-ons."*

It does this in a fast and simple way, compared to products like Amazon Web Services (AWS).

---

Fully-managed:
 
- No need to maintain servers, hardware or infrastructure.
- A ready-made environment for deploying apps

![](https://media.giphy.com/media/l41m0C1K4jVD5vQsM/giphy.gif)

---

- Create a new server in 10 seconds :star2: 
- Use `git push` for deployment.

---

Getting started:
:bulb: https://devcenter.heroku.com/articles/getting-started-with-nodejs

---

![](https://i.imgur.com/E7n7Nio.png)

---

![](https://i.imgur.com/bLG2TZY.png)

---

When you create an application on Heroku, it associates a new Git remote, typically named `heroku`, with the local Git repository for your application.

As a result, deploying code is just the familiar `git push`, but to the heroku remote instead:

![](https://i.imgur.com/epJvcBa.png)

---

![](https://i.imgur.com/WaCDvhZ.png)

---

![](https://i.imgur.com/D5pddSp.png)


---

![](https://i.imgur.com/ELYsDL0.png)

---

`https://lit-fjord-23988.herokuapp.com/`

or

![](https://i.imgur.com/1SjgPB7.png)

---

# Thanks Jo!

![](https://media.giphy.com/media/fnK0jeA8vIh2QLq3IZ/giphy.gif)

---

## What are environment variables and how can we change them?

---

# What?
<img src="https://media.giphy.com/media/5t9wJjyHAOxvnxcPNk/giphy.gif" height=400>  

---

A single app always runs in multiple environments, including at least on your development machine and in production on Heroku.

Although these environments might all run the same code, they usually have environment-specific configurations.

---

Environment variables are values that you only want to be accessible in certain environments - For example you may want to have a value that can only be viewed by yourself, or dynamically change the path of files that you want to serve.

---

## Why?
<img src="https://media.giphy.com/media/5BWVeEbJsaB4UZAzSz/giphy.gif" height=400>  

---

### Security:
<img src="https://media.giphy.com/media/81xwEHX23zhvy/giphy.gif" height=200>  

An app’s environment-specific configuration should be stored in environment variables (not in the app’s source code). This lets you modify each environment’s configuration in isolation, and prevents secure credentials from being stored in version control. These variables can then be accessed only where needed, such as limited to being seen only by your team or yourself.

---

### Flexibility:
<img src="https://media.giphy.com/media/z4cJCBqyDb5yOmf3GP/giphy.gif" height=200>  

You can reduce conditional statements like "If production server do X, else if test server do Y, else if localhost do Z..."

Not only does this make it easier for your code to transition effectively between different scenarios, but it also makes it easier to read.

---

## How?
<img src="https://media.giphy.com/media/LpR3R6vGn7xnJgseWy/giphy.gif" height=400>  

---

Environment variables are stored in a .env file. 

This is basically a plain text document that should be placed in the root of a project. In it you can specify the variables as key value pairs, and also add the file name to a .gitignore file to prevent it being tracked by Git.

---

- create a .env file
- ignore it in your .gitignore file
- use VS Code to edit your .envfile
- install the dotenv extension for VS Code
- install the npm extension for VS Code
- read the .envfile with the dotenv npm package as a dev dependency
- use the preloading option of dotenv to remove any runtime references to it
- use npm scripts to run your node app
- create a template file for your variables called .env.example

---

## How can we automatically deploy merges to our Main branch? :palm_tree: Chisha
  
 
---

### Automatically deploy merges to our main branch  

---

When you enable automatic deploys for a GitHub branch, Heroku builds and deploys all pushes to that branch. For example if you have a development app on Heroku, you can configure pushes to your GitHub development branch to be automatically built and deployed to that app

---

![](https://i.imgur.com/bSYHmSX.png)


---

### Automatically deploying merges to our main branch using Heroku

---

Pushing code from a Git repository to a Heroku app. You simply **add your Heroku app as a remote to an existing Git repository, then use git push to send your code to Heroku**. Heroku then **automatically builds your application and creates a new release**.

Because this method requires a developer with full access to manually push code to production, it's better suited for pre-production deployments or for projects with small, trusted teams.

---

**Pros**:
 - Simple to add to any Git-based workflow
 - Supports Git submodules
 
**Cons**:
 - Requires access to both the Git repository and Heroku app

---

If you’ve configured your GitHub repo to use automated Continuous Integration you can check the **“Wait for CI to pass before deploy”** checkbox. When enabled, Heroku will only auto-deploy after all the commit statuses of the relevant commit show success.

This commit won’t auto-deploy because one of the checks shows a pending status.

---

![](https://i.imgur.com/G442ZGO.png)

---

This commit will auto-deploy because all of the checks show a status of success: Success commit statuses - will auto-deploy.

![](https://i.imgur.com/I2mOMhe.png)


---

![](https://miro.medium.com/max/832/1*QwRfXqOe4UJlXhesWiUyCw.png)

---

### Manually deploy merges to our main branch :palm_tree: 

When you manually deploy to a branch, you can create an immediate deployment of any branch from the GitHub repo that’s connected to your app. We use manual deployment of merges to a branch, if you want to control **when changes** are deployed to Heroku.

https://www.heroku.com/flow

---

You can also use manual deploy to temporarily deploy a branch other than the one that’s configured for automatic deployment. 

---

For example:
 - You might have a development app synced to the development GitHub branch, but you temporarily want to test a feature branch. 
 - Simply trigger a manual deploy of the feature branch to test it on the Heroku app. 
 - Note that release of the feature branch is overwritten on the next successful GitHub push to the development branch.

---

### Thank you for listening :ear: 

![](https://media.tenor.com/images/21a157d32539f95c14c95899bce099a6/tenor.gif)
