---
title: Sweet CICD for my Portfolio
date: "2022-03-23"
eleventyExcludeFromCollections: true
---

# What my current setup is?
My portfolio is hosted on Github pages. Github pages has support for selecting the directory to host.
The options are "root" or "/docs" directories. 

I build my portfolio locally in "/docs" directory and push it. I chose "/docs" to host in Github pages on master branch.

This setup is a bit tedious. There are 2 problems.
- The build is in master repo
- I have to track the build in git

# What I want?
I want to solve both problems. I do not want to track the build and I want it to be in seperate repo.

# My weapon of choice - Github Actions
It has good documentation and I got comfortable with it very fast. There are 4 entities in a GA script.

## Events
When to trigger the script.

## Jobs
Steps to run in the script. It could be a shell script or an Action.

## Actions
Custom applications made to achieve specific functionality. You can write your own actions.

## Runners
Environment to run the workflow in. Github provides Windows, Macos, Ubuntu Linux. You can host your own runners as well.

# Automating it

# An issue I ran into
