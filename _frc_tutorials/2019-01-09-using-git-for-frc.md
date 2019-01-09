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


**This workflow will work well for our purposes, be sure to use it each time you 
commit.**
- Pull changes from your fork/branch
- Pull from origin master
- Resolve merge conflicts
- Make changes and make sure your changes work
- Stage changed files
- Commit staged files
- Pull changes from origin master (again)
- Resolve merge conflicts and commit
- Push changes to your fork/branch
- Submit a pull request to the main repository

# Tutorial

Git is a tool to manage different versions of a project, possibly shared between
multiple users. 

First let's setup Github. Github is a website (made by different
people than git) which remotely stores git repositories, allowing collaboration
across people and places. Create a Github account and go to [
https://github.com/FalconX-Robotics/roboRIO_2019](
https://github.com/FalconX-Robotics/roboRIO_2019). Then click fork (circled in
red below and choose your account name from the popup. This forks the repository
into your account; you will be making changes to this forked repository and
submitting pull requests to the main repository. Navigate to your cloned
repository in the browser.

![Forking](/assets/images/git-github-fork-ss.png){: width="100%" class="responsive"}

If you are on windows, the next step will require downloading [Git for Windows](
://gitforwindows.org/). Default options are okay for the entire installation.
Then, open VSCode, or close and reopen it if it's already open. 

Many git commands can be accessed in VSCode through the Ctrl-Shift-P shortcut,
like many WPILib related commands. Press Ctrl-Shift-P and type Git clone, and an
option should pop up to clone a repository. Select that option and enter the URL
obtained from the dialog in the blue circle above under clone with HTTPS.
Get this URL from **your** repository (make sure you clone your repository, not the
team's, as otherwise it may lead to confusion later). Select the directory on
your computer where you want to store the project.

Now we will configure git. Open git bash and type the following two commands
(pressing enter after each one).

{% highlight shell %}
git config --global user.name "<your name>"
git config --global user.email "<your email>"
{% endhighlight %}

Note the quotation marks, and make sure to replace \<your name\> with your
actual name and \<your email\> with the email you used to sign up to Github.
These commands configure your commit signature to use your name and email. Next,
with git bash navigate to your project folder. You can list the contents of the
current folder you are in with the command
{% highlight shell %}
ls
{% endhighlight %}
and change folders to a subfolder of the current folder with the command
{% highlight shell %}
cd
{% endhighlight %}

Once you have navigated to your project directory, run the command

{% highlight shell %}
git remote add base <URL>.
{% endhighlight %}

**This time get the URL from the team project** (in the same "clone with HTTPS"
dialog).

Now your are all set up to use git with VSCode. You can make changes to the
project using the techniques above





# "Advanced" Techniques
TODO: add "advanced" techniques (these techniques won't actually be advanced,
just further git features that you should eventually learn to use).


TODO: add instructions for how to set git bash as your shell inside VSCode so
you can use shell git commands within VSCode
