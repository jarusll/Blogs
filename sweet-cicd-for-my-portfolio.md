---
title: Sweet CICD for my Portfolio
date: 2022-03-23
---

Edit: 19/02/2023
Overengineered af, but was fun. 10/10 Would do it again.
# Sweet CICD for my Portfolio
## What my current setup is?
My portfolio is hosted on Github pages. Github pages has support for selecting the directory to host.
The options are "root" or "/docs" directories.

I build my portfolio locally in "/docs" directory and push it. I chose "/docs" to host in Github pages on master branch.

This setup is a bit tedious. There are 2 problems.
- The build is in master repo
- I have to track the build in git

## What I want?
I want to solve both problems. I do not want to track the build and I want it to be in seperate repo.

## My weapon of choice - Github Actions
It has good documentation and I got comfortable with it very fast. There are 4 entities in a GA script.

### Events
When to trigger the script.

### Jobs
Steps to run in the script. It could be a shell script or an Action.

### Actions
Custom applications made to achieve specific functionality. You can write your own actions.

### Runners
Environment to run the workflow in. Github provides Windows, MacOS, Ubuntu Linux. You can host your own runners as well.

## Automating it
Lets start by naming our github action first.
```github:name
name: build & push to gh-pages branch
```

I want the workflow to trigger when I push any change on master branch.

```github:on
on:
  push:
    branches:
      - master
```

The steps to build is pretty simple, I want to run the workflow on ubuntu-linux.

The Github action `actions/setup-node` is pretty self explanatory.
The Node version on my local is 14.18.1, so I decided to go with 14.x.

The Github action [`actions/checkout`](https://stackoverflow.com/questions/67131269/github-jobs-what-is-use-actions-checkout) checks out your repo.

After that its just installing the dependencies by `yarn install` and then building by `yarn build`
```github:jobs
jobs:
  build:

    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js 14.x
      uses: actions/setup-node@v1
      with:
        node-version: 14.x

    - name: yarn install
      run: |
        yarn install
    - name: yarn build
      run: |
        yarn run build
```

After building, I want to push the build directory to `gh-pages` repo.
There is an action available for it called [JamesIves/github-pages-deploy-action](https://github.com/JamesIves/github-pages-deploy-action).
This action copies the build dir `/docs` to `gh-pages` repo.
```github:deploy
    - name: Deploy
      uses: JamesIves/github-pages-deploy-action@v4.2.5
      with:
        branch: gh-pages # The branch the action should deploy to.
        folder: docs # The folder the action should deploy.

```

After the build has been made and copied to `gh-pages`, I can enable to Github pages for my repo for `gh-pages` branch on `root` directory.

## An issue I ran into

I have my `posts` as a git submodule in my portfolio repo. When `actions/checkout` checked out my portfolio repo, it did not fetch the submodule `posts`. As a result, no posts were rendered in the build. I solved this by manually cloning the `posts` repo.
```github:clone
    - name: Clone posts
      working-directory: ./src
      run: |
        git clone https://github.com/jarusll/posts.git
```

## Final script
```github:cicd.yml
name: build page

on:
  push:
    branches:
      - master

jobs:
  build:

    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js 14.x
      uses: actions/setup-node@v1
      with:
        node-version: 14.x

    - name: yarn install
      run: |
        yarn install

    - name: Clone posts
      working-directory: ./src
      run: |
        git clone https://github.com/jarusll/posts.git
    - name: yarn build
      run: |
        yarn run build

    - name: Deploy
      uses: JamesIves/github-pages-deploy-action@v4.2.5
      with:
        branch: gh-pages # The branch the action should deploy to.
        folder: docs # The folder the action should deploy.

```
