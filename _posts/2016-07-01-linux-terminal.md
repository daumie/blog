---
layout: post
title:  Linux Terminal
date:   2016-07-01 18:50:39
categories: terminal
---

The terminal is an interface which you can type and execute text based commands.

![my alternate text](/assets/img/terminal.png)


---

## Why Use It?

It can be much faster to complete some tasks using a Terminal than with graphical applications and menus. Another benefit is allowing access to many more commands and scripts.



A common terminal task of installing an application can be achieved within a single command, compared to navigating through the Software Centre or Synaptic Manager. 

For example the following would install **weechat**  IRC client:

	sudo apt-get install weechat

Sometimes you will also see the following notation:

	$whoami
	daumie
	$ls
	Downloads Documents

A similar notation is:

	# apt-get update

This means the command is being run as root, that is, using `sudo`

The `#` character is also used for comments.

	# this command will give you your username
	whoami
	# the following command will show the contents of the current directory
	ls -la

-----------------------------------------------------------------------------------------------------------

## Alternative names for the terminal:

   - Console
   - Shell
   - Command line
   - Command prompt

