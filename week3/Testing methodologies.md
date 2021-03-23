# Testing methodologies

---

## What is Test-Driven Development (TDD)? Can it help us write better code?

<img src="https://i.imgur.com/PlA15M8.gif" style="width: 350px;">

---

Relies on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases.<!-- .element: class="fragment" data-fragment-index="0" --> 

This is opposed to software being developed first and test cases created later.<!-- .element: class="fragment" data-fragment-index="1" --> 

---

![](https://i.imgur.com/hb2uGfS.png)

---

![](https://i.imgur.com/LeGakPy.png)

---

![](https://i.imgur.com/8IWFER4.png)

---

![](https://i.imgur.com/QW0tEF0.png)

---

![](https://i.imgur.com/z9DDGig.png)

---

![](https://i.imgur.com/uA5vzTJ.png)

---

**Real life example**
Fixing a shelf to the wall
<img src="https://i.imgur.com/kUCKRvc.gif" style="width: 250px;"><!-- .element: class="fragment" data-fragment-index="0" -->

1. Check drawn line is level on the wall by measuring. If test passes...<!-- .element: class="fragment" data-fragment-index="1" -->
2. ...drill first hole in wall. Then test again.<!-- .element: class="fragment" data-fragment-index="2" --> 
3. Last step would be to check if it is level<!-- .element: class="fragment" data-fragment-index="3" -->

---

Behaviour driven has very few unit tests.
1. Check if the shelf is level. If it is not level, simply adjust!

---

Coding example

https://www.youtube.com/watch?v=89Pl2Uok8xc


---

**Benefits**
- Improved test coverage, leads to 40-80% fewer bugs in production
- Takes a longer time to get the hang of, but after practice (~2 years) allows developers to code faster ultimately. 

---

## Behavior-Driven Development - Chisha and Antonio


---


### What is Behavior-Driven Development (BDD)? How do we translate user requirements into automated tests?


<img src="https://insights.daffodilsw.com/hs-fs/hubfs/test-driven-development-vs-behaviour-driven-development.gif?width=700&height=300&name=test-driven-development-vs-behaviour-driven-development.gif" style="width: 600px;">



---


**BDD is a _branch_ of TDD**. BDD uses human-readable descriptions of software user requirements as the basis for software tests.

![](https://vikramviknowledgesharing.files.wordpress.com/2017/01/bdd-workflow-600x268.png?w=600)


---

The **BDD** language used to encode the system test are **user acceptance tests**. It focuses exclusively on the **business value that a customer should get from the software** rather than **describing the user interface of the software**, or how the software should accomplish the goals.

<!--By using this language to capture requirements and then execute small specifications in the form of BDD tests we can ensure we are focusing on desireable intent of our software!-->

---

BDD focuses more on the behavior of the feature, whereas TDD focuses on capturing the accurate requirements.
![](https://miro.medium.com/max/581/1*V3CyC87v-5oj6icmWeu-fg.jpeg)

---

The language then follows ==two paths==:
 - Give the test a concrete technical meaning by turning the description into a ==domain specific language (DSL)== so that the human-readable description doubles as machine-readable code, (continue on the BDD path) or
 - Translate the ==user stories== into automated tests in a general-purpose language, such as JavaScript.

---

---

Either way always treat your tests as **Black Box Tests** meaning the test code should not care about the implementation of the feature you are testing. Based on the input you are passing you expect a specific output. The output can be a value.
![](https://phoenixnap.com/blog/wp-content/uploads/2018/11/black-approach.jpg)


---

How do we translate user requirements into automated tests? By creating a user story that.... 

```
Story: Transfers change balances
As a wallet user
In order to send money
I want wallet balances to update
Given that I have $40 in my balance
And my friend has $10 is their balance
When I transfer $20 to my friend
Then I should have $20 in my balance
And my friend should have $30 in their balance.

```


---

## Context: Staring State

- Starting state

---

## Event: What the user does 

- As a wallet user
- In order to send money

---

## Outcomes: The expected results 

* I want wallet balances to update
* Given that I have $40 in my balance
* And my friend has $10 is their balance
* When I transfer $20 to my friend
* Then I should have $20 in my balance
* And my friend should have $30 in their balance.

---



---

## Unit Tests vs Functional Tests

---

## Unit Tests

Unit tests are typically written by the implementing programmer, and test from the programmer’s perspective.

---

**Unit tests run very fast** because they’re not dependent on other parts of the system, and as such, typically have no asynchronous I/O to wait on. It’s much faster and less expensive to find and fix a flaw with unit tests than it is to wait for a complete integration suite to run. Unit tests typically complete in milliseconds, as opposed to minutes or hours.


---



---


**Units must be modular** in order to make it easy to test them in isolation from other units. This has the added benefit of being very good for the architecture of the application. Modular code is easier to extend, maintain, or replace because the effects of changing it are generally limited to the module unit under test. Modular applications are more flexible and easier for developers to work with over time.


---

## Functional Tests

Functional tests are informed by the user acceptance criteria and should test the application from the user’s perspective to ensure that the user’s requirements are met.

---

**Take longer to run**, because they must test the system end-to-end, integrating with all the various parts and subsystems the application relies on to enable the user workflow being tested. Large integration suites sometimes take hours to run. I’ve heard stories of integration suites that took days to run. I recommend hyper-optimizing your integration pipeline to run in parallel so that it can complete in under 10 minutes — but that’s still too long for developers to wait on every change.

---

**Ensure that the units** work together as a whole system. Even if you have excellent unit test code coverage, you still need to test your units integrated with the rest of the application. It doesn’t matter if NASA’s heat shields work if they don’t stay attached to the rocket on reentry. Functional tests are a form of system tests which ensure that the system as a whole behaves as expected when it’s fully integrated.

---

## What is test coverage? Can this tell us about the quality of our tests? - Maryam

---

<img src="https://i.imgur.com/aeW4uxW.jpg" style="width: 600px;">


---

```
(50 / 500) * 100 = 10%
```


---

- Test coverage is a useful  for finding untested parts of a codebase.
![](https://i.imgur.com/69Fa7TL.gif)

---

- Low coverage number is not a good sign **BUT**
![](https://i.imgur.com/nMJOVrY.png)

---

- Considering parts of code, that is what really matters
![](https://i.imgur.com/5gxDmuX.jpg)

---

![](https://i.imgur.com/LssQrul.png)

---

I would say you are doing enough testing if the following is true:

You rarely get bugs that escape into production, and
You are rarely hesitant to change some code for fear it will cause production bugs.
