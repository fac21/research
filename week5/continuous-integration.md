
## Continuous Integration 
Craig, Mariya, Michael, Safia


---

### **What is continuous integration?**
![](https://media.giphy.com/media/xT0xeuOy2Fcl9vDGiA/giphy.gif)

---

### **CI/CD Pipeline**
![](https://i.imgur.com/IR3mEG8.png)

---

Continuous integration (CI) is the practice of automating the integration of code changes from multiple contributors into a single software project. 
***
It's a primary DevOps best practice, allowing developers to frequently merge code changes into a central repository where builds and tests then run.

---

![](https://i.imgur.com/gOAg9Fq.png)


---

Building and testing your code requires a server. You can build and test updates locally before pushing code to a repository, or you can use a CI server that checks for new code commits in a repository.


---

Continuous integration isn’t a tool in iself, it’s a larger framework with a set of practices aided by certain tools.

---

<!-- Craig -->
## What does a CI Server do?

<img src="https://media.giphy.com/media/dAE5CVdZEJ6dyFGycy/giphy.gif" style="float: right" height=250> A continuous integration server (sometimes known as a build server) essentially manages the shared repository and acts as a referee for the code coming in.   

When developers commit to the repository, the CI server initiates a build and documents the results of the build.

---

## How it works:

1. Monitors the repository and checks out changes when they occur
2. Builds the system and runs unit and integration tests
3. Releases deployable artefacts for testing
4. Assigns a build label to the version of the code it just built
5. Informs the team of the successful build
-- If the build or tests fail, the CI server alerts the team

---

![](https://i.imgur.com/BvwdvxP.png)

---

### Advantages of using a CI server:

---

#### Automated tests!

<img src="https://media.giphy.com/media/dtsD7ZvZJhfs7RktCw/giphy.gif" height=200>

When code is committed using a CI Server, errors in the code are detected automatically. 
The server tests the code and provides feedback to the committer quickly, without the committer having to initiate a manual build.

---

#### Better collaboration!

<img src="https://media.giphy.com/media/0Av9l0VIc01y1isrDw/giphy.gif" height=200>

Instead of relying on developers to keep the shared repository up to date, the CI server manages all code coming in and maintains the integrity of the source code through automatic builds and tests. 
This allows developers to focus on their own projects instead of worrying about other projects breaking their tests. 

---

#### Streamlined workflow!

<img src="https://media.giphy.com/media/Btn42lfKKrOzS/giphy.gif" height=200>

Without CI servers, developers are working on different layers of the application with code saved on local machines. 
While teams that do self-hosted testing can get around these potential issues, a CI server takes this extra layer of coordination out of the workflow.

---

### i.e. 
### Teams can collaborate without worrying about code.
<img src="https://media.giphy.com/media/UTLzsXBovpJnZfFcaL/giphy.gif">

---

<!-- Michael -->
### How can we use GitHub Actions to automatically run our tests and deploy our code?

---

![](https://media.giphy.com/media/dUfWrSUz7MUsyJHRbp/giphy.gif)

---

Github Actions is a Continuous Integration (CI) + Continuous Deployment (CD) tool by Github.

---

Continuous Integration: People push to a Git repository and the code gets tested automatically.
***
Continuous Delivery: The pushed code (ideally having been tested) is then pushed into the server so it becomes live for users.

---

Getting set up

- Create a Github repo
- Clone your repo to your local device
- Install node JSON pacakges

---

run ==`npm init-y`== in the CLI to get your package.json file set up

---

![](https://i.imgur.com/XrbEuWE.png)

---

Create `action.yml` file

---

![](https://i.imgur.com/SNH6FpR.png)

---

![](https://i.imgur.com/Zkrgd4H.png)
![](https://i.imgur.com/55I8TwC.png)

---

![](https://i.imgur.com/9JBOHzI.png)

---

![](https://i.imgur.com/vDiPKyL.png)

---

![](https://i.imgur.com/Ujck9Dv.png)

---

![](https://i.imgur.com/oKW8uJy.png)

---

![](https://i.imgur.com/GBStRI7.png)
![](https://i.imgur.com/l6piKVf.png)
![](https://i.imgur.com/76QqhNe.png)

---

Create file directory `github/workflows/main.yml`

![](https://i.imgur.com/BSDWG8k.png)

---

![](https://i.imgur.com/ol3nyaB.png)

---

![](https://i.imgur.com/kAfLmvW.png)

---

![](https://i.imgur.com/7f7pkAC.png)

---

![](https://i.imgur.com/vNg3fiH.png)

---

![](https://i.imgur.com/J8ToDVB.png)

---

![](https://i.imgur.com/UTnY3Cf.png)

---

https://www.youtube.com/watch?v=COPS4VMfaUc&ab_channel=CodewithAniaKub%C3%B3w

---

<!-- Mariya -->
### Why might we want to run our tests whenever we push code to our repo?

---

Tests are an important part of any project that allow us to make sure we're not breaking existing code while we work. While they're important, they're also easy to forget about.
![](https://media.giphy.com/media/ZaQXJIQjpBvRWchjsA/giphy.gif)

---

<img style="float: right;" src="https://media.giphy.com/media/2ywmJmkOxlsIsHKLC0/giphy.gif" width="300">

If you are tired of forgetting to run tests before pushing to your repositories or maybe you just want to up your automation game you will definitely want to run your tests whenever you push code to your repo. 

### But there are some other advantages. 

---

<!-- As Craig said, -->
Continuous Integration is a way to increase code quality without putting an extra burden on the developers. 
![](https://media.giphy.com/media/jOawfvTuyfZSYNCBu0/giphy.gif)
Tests and checks of your code are handled on a server and automatically reported back to you.

Using it helps you to: 

---

<img style="float: right;" src="https://media.giphy.com/media/34804BGdviQ1mKLBUd/giphy.gif" width="300">

### 1. Run your tests in the real world
 If you ever had your tests pass on your machine, but fail on someone else's, with CI you can avoid that embarrassment. Just push your code to your new branch and the CI server will take care of running the tests for you. If everything is green, you can be sure that you didn't break anything. And if they fail for someone else, you have evidence that they are wrong.

---

### 2. Increase your code coverage
If you think your tests cover most of your code, you better think again. A CI server can check your code for test coverage. Now, every time you commit something new without any tests, you will feel the shame that comes with having your coverage percentage go down because of your changes.

---

### 3. Deploy your code to production
You can have the CI server automatically deploy your code to production if all the test within a given branch are green or <!-- as Michael said --> what is formally known as __Continuous Deployment__, or __Oh my God, that was scary, I'm glad my code worked!__ in some circles.

![](https://media.giphy.com/media/S4BaMhHY4d21V7USSf/giphy.gif)

---

<img style="float: right;" 
src="https://media.giphy.com/media/3ohhwlgaHwZ9zQ9HZS/giphy.gif" width="300">
### 4. Decrease code review time
You can have your CI and Version Control Server communicate with each other and tell you when a merge request is good to merge. It can also show how the code coverage would be affected by it. This can dramatically reduce the time it takes to review a merge request.

---

So, testing every time you push your code will ensure that a codebase does not get updated with changes that could break something and will make your life easier.
![](https://media.giphy.com/media/piO6cmvxIK0A05MNkY/giphy.gif)

---

### Thank you for listening! Any Questions?
![](https://media.giphy.com/media/lD76yTC5zxZPG/giphy.gif)


---

### Resourses:

[Learn How to Set Up a CI/CD Pipeline From Scratch](https://dzone.com/articles/learn-how-to-setup-a-cicd-pipeline-from-scratch)

[Understanding how to use Github Actions](https://zellwk.com/blog/understanding-github-actions/)


[About continuous integration- GitHub Docs](https://docs.github.com/en/actions/guides/about-continuous-integration)

[What is CI/CD?](https://www.infoworld.com/article/3271126/what-is-cicd-continuous-integration-and-continuous-delivery-explained.html)

[What is Continuous Integration? - YouTube](https://www.youtube.com/watch?v=1er2cjUq1UI)

[GitHub Actions Tutorial - Basic Concepts and CI/CD Pipeline with Docker - YouTube](https://www.youtube.com/watch?v=R8_veQiYBjI)

---
