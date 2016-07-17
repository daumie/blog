---
layout: post
title: Git Basics
date:   2016-07-17 02:50:39  
categories: git
---

## Installing Git

The official website of Git has [detailed information about installing](http://git-scm.com/book/en/Getting-Started-Installing-Git) on Linux, Mac, or Windows. In this case, we would be using Ubuntu 16.04 LTS for demonstration purposes, where you install Git using `apt-get` _(package management command line program)_.

	$ sudo apt-get install git

### Initial Configuration

	$ mkdir demo_project
	$ cd demo_project

The first step is to initialize Git in a directory. This is done using the command `git init`, which creates a *.git* directory that contains all the <u>Git-related information</u> for your project.

	┌─[daumie@casper] - [~] - [Sun Jul 17, 02:13]
	└─[$] <> mkdir demo_project
	┌─[daumie@casper] - [~] - [Sun Jul 17, 02:13]
	└─[$] <> cd demo_project 
	┌─[daumie@casper] - [~/demo_project] - [Sun Jul 17, 02:14]
	└─[$] <> git init 
	Initialized empty Git repository in /home/daumie/demo_project/.git/
	┌─[daumie@casper] - [~/demo_project] - [Sun Jul 17, 02:14]
	└─[$] <git:(master)> 

Next, we need to configure our name and email. You can do it as follows, replacing the values with your own name and email.

	$ git config --global user.name 'daumie'
	$ git config --global user.email 'dominic.motuka@gmail.com'
	$ git config --global color.ui 'auto'

It is important to note that if you do not set your name and email, certain default values will be used. In our case, the username ‘daumie’ and email ‘daumie@casper’ would be the default values.

Also, we set the UI color to `auto` so that the output of Git commands in the terminal are color coded. The reason we prefix `--global` to the command is to avoid typing these config commands the next time we start a Git project on our system._(Changes will be applied system wide)_

### Staging Files for Commit

The next step is to create some files in the directory. You could use a text editor like Vim. Note that if you are going to add Git to an already existing directory, you do not need to perform this step.You can simply create files using touch command.

	$ touch hello.html

#### Check the Status of Your Repository

Now that we have some files in our repository, let us see how Git treats them. To check the current status of your repository, we use the `git status` command.

	$ git status
	On branch master

	Initial commit

	Untracked files:
	(use "git add <file>..." to include in what will be committed)

	hello.html

	nothing added to commit but untracked files present (use "git add" to track)


#### removing files

Let’s say you have added files to Git that you do not want it to track. In such a situation, you tell Git to stop tracking them. Yet, running a simple `git rm` will not only remove it from Git, but  [will also remove it from your local file system](http://stackoverflow.com/questions/1143796/git-remove-a-file-from-the-repository-without-deleting-it-from-the-local-filesy) as well! To tell Git to stop tracking a file, but still keep it on your local system, run the following command:

	$ git rm --cached [file_name]



#### Staging and committing

A staging step in git allows you to continue making changes to the working directory, and when you decide you wanna interact with version control, it allows you to record changes in small commits.

Suppose you have edited three files _(a. html, b. html, **and** c. html)_. After that you need to commit all the changes so that the changes to `a. html` and `b. html` were a single commit, while the changes to `c. html` were not logically associated with the first two files and were done in a separate commit.

In theory you can do the following:

	git add a.html
	git add b.html
	git commit -m "Changes for a and b"
	git add c.html
	git commit -m "Unrelated change to c"

Separating staging and committing, you get the chance to easily customize what goes into a commit.

##### Committing changes 

Well, enough about staging. Let’s commit the staged changes to the repository.

	$ git commit -m "Initial commit"

When you used git commit for committing the first hello.html version to the repository, you included the -m flag that gives a comment on the command line. The commit command allows interactively editing comments for the commit. And now, let’s see how it works.

If you ommit the -m flag from the command line, git will pop you into the editor of your choice from the list (in order of priority):

	
    GIT_EDITOR environment variable
    core.editor configuration setting
    VISUAL environment variable
    EDITOR environment variable

###### Checking the status

At the end let us check the status.

	$ git status
	# On branch master
	nothing to commit (working directory clean)

The working directory is clean, you can continue working.