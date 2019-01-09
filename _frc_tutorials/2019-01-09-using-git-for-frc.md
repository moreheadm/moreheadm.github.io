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
people than Git) which remotely stores Git repositories, allowing collaboration
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

Many Git commands can be accessed in VSCode through the Ctrl-Shift-P shortcut,
like many WPILib related commands. Press Ctrl-Shift-P and type Git clone, and an
option should pop up to clone a repository. Select that option and enter the URL
obtained from the dialog in the blue circle above under clone with HTTPS.
Get this URL from **your** repository (make sure you clone your repository, not the
team's, as otherwise it may lead to confusion later). Select the directory on
your computer where you want to store the project.

Now we will configure Git. Open Git Bash and type the following two commands
(pressing enter after each one).

{% highlight shell %}
git config --global user.name "<your name>"
git config --global user.email "<your email>"
{% endhighlight %}

Note the quotation marks, and make sure to replace \<your name\> with your
actual name and \<your email\> with the email you used to sign up to Github.
These commands configure your commit signature to use your name and email. Next,
with Git Bash navigate to your project folder. You can list the contents of the
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

Now your are all set up to use Git with VSCode. You can make changes to the
project using the workflow above. The rest of this section will be going over
how to do these.

Accessing Git in VSCode is done through the icon on the side of the of the page
that looks something like a tuning fork (it's the third one down). Changes to
files show up in the toolbar, and you can stage them for commit by pressing the 
"plus" symbol next to the change. Once ready to commit, you can type a commit
message in the textbox, and press Ctrl-Enter.

The push and pull commands (as well as many others) can be accessed either
through the "three dot" menu on the Git toolbar, or through Ctrl-Shift-P. Use
"pull from..." and "push to..." and select a remote. You want to push only to
your remote (origin), but pull from the team remote (base) and your remote, as
described in the workflow.

Resolving merge conflicts can be tricky. Whenever there is a conflict between
two people code, it will show up as strange symbols in the source code files.
The symbols will separate the two versions of the code. Manually edit the
affected files, so that they work the way you want, remove the added symbols and
potentially duplicate functionality. Commit after resolving the merge conflict.

Submitting a pull request is done through the Github online interface.

Note that all these operations can be done from the command line with Git Bash.

# "Advanced" Techniques
TODO: add "advanced" techniques (these techniques won't actually be advanced,
just further Git features that you should eventually learn to use).


TODO: add instructions for how to set git bash as your shell inside VSCode so
you can use shell git commands within VSCode
