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
I want to solve both problems. I do not want to track the build and I want the build to be in seperate repo.

# My weapon of choice - Github Actions

# Automating it

# An issue I ran into
