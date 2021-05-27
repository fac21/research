## GitHub Actions CI
![](https://media.giphy.com/media/l2R06WPHU4ae0H4LC/giphy.gif)

Antonio, Nafisa, Safia & Sevda

---

![](https://i.imgur.com/7xRytKH.png)

---


**Continuous Integration**: People push to a Git repository and the code gets tested automatically.

**Continuous Delivery**: The pushed code (ideally tested and bug-free) is then pushed into the server so it becomes live for users.

---

![](https://i.imgur.com/rLKO42b.png)

---

## Create CI Workflow or Pipeline

- Whenever the repo is created the "Actions" Tab is integrated to it which at the top part of your GitHub repo. 

- Choose on of the workflows that matches technologies your ptoject use by clicking "Set up Workflow" button.

---

- It automatically creates configuration view in your project: `my-project/.github/.workflows/.file.yml` which holds the workflow logic.

- Start commit by creating a new branch and PL. 

---

`on:` is a section where we define the events that triggers the workflow on the `jobs:` section!

`jobs:` groups set of actions that will be executed

<img src="https://i.imgur.com/HNIBqpj.png" alt="" width="400" height="500">

---

[Documentation for complete list of events: ](https://https://docs.github.com/en/actions/reference/events-that-trigger-workflows)

[Documentation for complete list of actions:](https://github.com/marketplace/actions/)

---

<!-- Safia -->
### GitHub Marketplace 
***
is a central location for you to find actions created by the GitHub community

---

### Cypress GitHub Action

1. Install npm dependencies.
2. Build the project ( npm run build )
3. Start the project web server ( npm start )
4. Run the Cypress tests within our GitHub repository

---

### Setup 
- GitHub Action configuration is placed within .github/workflows/main.yml.
```yaml=
name: Cypress Tests

on: [push]

jobs:
  cypress-run:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      # Install NPM dependencies, cache them correctly
      # and run all Cypress tests
      - name: Cypress run
        uses: cypress-io/github-action@v2
        with:
          build: npm run build
          start: npm start
```

---

### How this action works:

On push to this repository, this job will provision and start GitHub-hosted Ubuntu Linux instance for running the outlined steps for the declared cypress-run job within the jobs section of the configuration.

The GitHub checkout Action is used to checkout our code from our GitHub repository.

---

Finally, our Cypress GitHub Action will:
- Install npm dependencies
- Build the project (npm run build)
- Start the project web server (npm start)
- Run the Cypress tests within our GitHub repository within Electron.

---

[Cypress GitHub Marketplace](https://github.com/marketplace/actions/cypress-io)
![](https://i.imgur.com/qHD51Qt.png)

---

<!-- Nafisa -->
Once you've set up your Github action workflow file, 
you'll then want to prevent merges for code that fails 
the tests:

Settings➡ Branches ➡️ Add Rule

set the branch name pattern to * (which means all branches)

---

check the Require status checks to pass before merging option

then select all of our different status checks that we'd like to require to pass before merging and then click on Create.

---

![](https://i.imgur.com/xJVh3Iy.png)

---

Now you should be unable to merge code that fails your tests.
![](https://i.imgur.com/XXgwNBQ.png)

---

## Pro

+ Easy integration with many different tools. 

---

![](https://i.imgur.com/fDjCcvl.png)

---

<!-- Antonio -->
## Testing Frameworks

---

Test Automation Framework as a set of guidelines for creating and designing test cases. It is a conceptual part of the automated testing that helps testers to use resources more efficiently.

---

<img src="https://i.imgur.com/iCa5T3Q.png" width="300px"/>

---

![](https://media.giphy.com/media/l4FAPaGGeB7D1LfIA/giphy.gif)

---

## Resources:

[Events that trigger Workflows](https://docs.github.com/en/actions/reference/events-that-trigger-workflows)

[Next.js website deployment](https://www.freecodecamp.org/news/how-to-use-github-actions-to-deploy-a-next-js-website-to-aws-s3/)

[Cypress](https://github.com/marketplace/actions/cypress-io)

[ Week 5 - Continous Intergration Spike Presentation](https://github.com/fac21/research/blob/main/week5/continuous-integration.md)

[GitHub Actions | Cypress Documentation ](https://docs.cypress.io/guides/continuous-integration/github-actions#Cypress-GitHub-Action)

---
