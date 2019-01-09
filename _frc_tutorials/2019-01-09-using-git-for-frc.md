---
layout: post
title: "Using Git for FRC"
categories: frc
tags: [frc, git]

---

This post will cover how to use Git for FRC with VSCode. It's intended both as
a cheatsheet and a tutorial. It's mostly designed for Team 6662.

# Git Cheetsheet

<!--Clone a repository
{% highlight shell %}
git clone <repo name>
{% endhighlight %}

Check status of repository
{% highlight shell %}
git status
{% endhighlight %}-->

**Workflow: Pull changes from your fork/branch, pull from origin master, resolve
merge conflicts, make changes, make sure your changes work, stage changed files
with git add, commit staged files

# Tutorial

Git is a tool to manage different versions of a project, possibly shared between
multiple users. 

First let's setup Github. Github is a website (made by different
people than git) which remotely stores git repositories, allowing collaboration
across people and places. Create a Github account and go to [
https://github.com/FalconX-Robotics/roboRIO_2019](
https://github.com/FalconX-Robotics/roboRIO_2019). Then click fork and choose
your account name from the popup. This forks the repository into your account;
you will be making changes to this forked repository and submitting pull
requests to the main repository.

![Forking](/assets/images/git-github-fork-ss.png){: width="100%" class="responsive"}




# "Advanced" Techniques
TODO: add


TODO: add instructions for how to set git bash as your shell inside VSCode so
you can use shell git commands within VSCode
