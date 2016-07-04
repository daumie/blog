---
layout: post
title: Basic Linux Commands
date:   2016-06-21 18:50:39
categories: terminal
---

 From my past experience when I was new to **Nux** , commands and terminal really scared me, I was worried about the commands to the extent I had to remember and memorise them to get myself fully functional with Linux.  I strongly believed that there should be an article with details of commands in easy to learn and understand language.This article is a step towards it.

## ls

The command `ls` stands for _List Directory Contents_, List the contents of the folder, be it file or folder, from which it runs

	$ ls
	Desktop  Documents  Downloads  mp3blaster-3.2.5  Music  Pictures  Public  scripts  Templates  Videos  weechat.log  workspace

The command `ls -l` list the content of folder, in long listing fashion.

	$ ls -l
	total 56
	drwxr-xr-x  2 daumie daumie  4096 Jun 29 23:24 Desktop
	drwxr-xr-x  5 daumie daumie  4096 Jun 10 17:22 Documents
	drwxr-xr-x  5 daumie daumie 12288 Jun 29 20:07 Downloads
	drwxrwxr-x  6 daumie daumie  4096 Jun 29 20:09 mp3blaster-3.2.5
	drwxr-xr-x 39 daumie daumie  4096 Jun 10 14:11 Music
	drwxr-xr-x  3 daumie daumie  4096 Jun 28 20:48 Pictures
	drwxr-xr-x  2 daumie daumie  4096 Feb 11 19:46 Public
	drwxrwxr-x  2 daumie daumie  4096 May 31 16:52 scripts
	drwxr-xr-x  2 daumie daumie  4096 Feb 11 19:46 Templates
	drwxr-xr-x  8 daumie daumie  4096 Jun 24 19:29 Videos
	drwxr-xr-x 12 daumie daumie  4096 Jun  4 22:28 weechat.log
	drwxrwxr-x 16 daumie daumie  4096 Jun 29 11:36 workspace

Command `ls -a`, lists the content of folder, including hidden files starting with `.`

	$ ls  -a
	.              .config          .gemrc                 .local            Public                     .vimrc                   .zlogin
	..             .corkscrew-auth  .gitconfig             .macromedia       .rvm                       .vim_runtime             .znc
	.adobe         .dbus            .gitconfig.backup      .mkshrc           scripts                    .weechat                 .zsh_history
	.atom          Desktop          .gitconfig.local       .mozilla          .ssh                       weechat.log              .zshrc
	.bash_history  .dmrc            .git-credential-cache  mp3blaster-3.2.5  .sudo_as_admin_successful  .wget-hsts               .zshrc.backup
	.bash_logout   Documents        .gitignore             Music             .telegram                  workspace                .zshrc.pre-oh-my-zsh
	.bash_profile  .dotfiles        .gksu.lock             .nano             Templates                  .Xauthority              .zsh-update
	.bashrc        Downloads        .gnupg                 .oh-my-zsh        .thunderbird               .xsession-errors
	.bundle        .fonts           .i3status.conf         Pictures          Videos                     .xsession-errors.old
	.cache         .gconf           .ICEauthority          .pki              .viminfo                   .zcompdump
	.compiz        .gem             .irbrc                 .profile          .vim_mru_files             .zcompdump-casper-5.1.1

---

## mkdir

The `mkdir` _Make directory_ command creates a new directory with name path. However if the directory already exists, it will return an error message _cannot create folder, folder already exists_

	$ mkdir ~/stuff

` $ mkdir -p ` will make an entire path even if all the directories don't exist

[**Question**]: How dow we remove directories?.....worry no more, linux has you covered

	$ rmdir ~/stuff

If you wish to create a subdirectory _say the directory **bar**_ inside another directory _say the directory **foo**_ but you are not sure whether this one exists or not, you can ensure to create the subdirectory and _if needed_ its parent directory without raising errors by typing:

	$ mkdir -p ~/foo/bar

[**Question**] What if we need to create a file?.........not too fast :-)

---

## `touch` Command

The `touch` command stands for _Update the access and modification times of each FILE to the current time_. `touch` command creates the file, only if it doesn’t exist. If the file already exists it will update the timestamp and not the contents of the file.

	$ touch filename

Note: `touch` can be used to create file under directory, on which the user has write permission, only if the file don’t exist there.


	$ touch ~/foo/bar/filename

---

## command `apt`

The Debian based `apt` command stands for _(Advanced Package Tool)_. `apt` is an advanced package manager for Debian based system _(Ubuntu, Kubuntu, etc.)_, that automatically and intelligently **search**, **install**, **update** and **resolves dependency** of packages on _Gnu/Linux_ system from command line.

	root@casper :- # apt-get update
	Get:1 http://security.ubuntu.com/ubuntu xenial-security InRelease [94.5 kB]                                                                            
	Hit:2 http://us.archive.ubuntu.com/ubuntu xenial InRelease                                                                                             
	Hit:4 http://ppa.launchpad.net/fossfreedom/rhythmbox-plugins/ubuntu xenial InRelease                                                                   
	Hit:5 http://ppa.launchpad.net/git-core/ppa/ubuntu xenial InRelease                                                                                    
	Get:6 http://us.archive.ubuntu.com/ubuntu xenial-updates InRelease [94.5 kB]                                                                           
	Get:3 http://screenshots.getdeb.net xenial-getdeb InRelease [8,139 B]                                                                                  
	Get:7 http://ppa.launchpad.net/kvirc/kvirc/ubuntu xenial InRelease [18.1 kB]                                                                           
	Hit:8 https://deb.nodesource.com/node_4.x xenial InRelease                                                                                             
	Hit:11 http://ppa.launchpad.net/noobslab/icons/ubuntu xenial InRelease                                                                                 
	Get:9 http://screenshots.getdeb.net xenial-getdeb/apps amd64 Packages [57.6 kB]

Note: The above commands results into system-wide changes and hence requires _root password_ (Check `#` and not `$` as prompt). `apt` is considered more advanced and intelligent as compared to _`yum` command_.

---

## cat & less commands

The `cat` stands for _(Concatenation)_. Concatenate **(join)** two or more plain file and/or _print contents of a file on standard output_
	
	$cat myspeech.txt
	Countrymen, ladies and comrades lend me your ears!

Here, `cat` just opens the file _myspeech.txt_ and prints the entire file to
your screen, as fast as it can

The `less` command when working on the command line allows you to view the contents of a file allowing you to navigate through a long file. You can use it directly on a file or in conjunction with the cat command where the cat command prints the file to screen and the `less` command controls how you view the contents.

You use the `less` command like this:

	$ `less` /some/directory/filename

You use the pipe command to pipe the output of the `cat` to the `less` command like this:

	$ cat /some/directory/filename | less

The `less` command will print the first screen full of data from that file to your screen.

To traverse the file press the following.

_down arrow - scrolls down one line_

_up arrow - scrolls up one line_

_d - scrolls down half a page_

_b - scrolls up half a page_

_q - exit `less`_

 

For more control of the less command check out the man pages by typing:

	$ man less


**Note:** `>>` and `>` are called append symbol. They are used to append the output to a file and **NOT** on standard output. `>` symbol will delete a file already existed and create a new file hence for security reason it is advised to use `>>` that will write the output without overwriting or deleting the file.

Before Proceeding further, I must let you know about wildcards  Wildcards are a shell feature that makes the command line much more powerful than any GUI file managers. You see, if you want to select a big group of files in a graphical file manager, you usually have to select them with your mouse. This may seem simple, but in some cases it can be very frustrating.



For example, suppose you have a directory with a huge amount of all kinds of files and subdirectories, and you decide to move all the HTML files, that have the word “Linux” somewhere in the middle of their names, from that big directory into another directory. What’s a simple way to do this? If the directory contains a huge amount of differently named HTML files, your task is everything but simple!

In the Linux CLI that task is just as simple to perform as moving only one HTML file, and it’s so easy because of the shell wildcards. These are special characters that allow you to select file names that match certain patterns of characters. This helps you to select even a big group of files with typing just a few characters, and in most cases it’s easier than selecting the files with a mouse.

---


|  **Wildcard**     | **Matches**                                   |
| :-------------: |:------------------------------------------:|
|       `*`       | zero or more characters                   |
| 		`?`       | exactly one character                      |
|     `[abcde]`   | exactly one character listed              |   
| 	  `[a-e]`     | exactly one character in the given range   |
|	  `[!abcde]`  | any character that is not listed           |
|	  `[!a-e]`    | any character that is not in the given range |
| `{debian,linux}`| exactly one entire word in the options given |

---

## command `cal`

The 'cal' _Calendar_, it is used to displays calendar of the present month or any other month of any year that is *advancing* or *passed*.

	$ cal

	June 2016        
	Su Mo Tu We Th Fr Sa  
	          1  2  3  4  
	 5  6  7  8  9 10 11  
	12 13 14 15 16 17 18  
	19 20 21 22 23 24 25  
	26 27 28 29 30    

Show calendar of year **1738** for month **February**, that already has passed.

	$ cal 02 1738

	February 1738      
	Su Mo Tu We Th Fr Sa  
	          1  2  3  4  
	 5  6  7  8  9 10 11  
	12 13 14 15 16 17 18  
	19 20 21 22 23 24 25  
	26 27 28    


**Note:** You don't need to flip the calendar  50 years back, neither  do you need to make complex mathematical calculation to know which day you were worn or your coming birthday will fall on which day.

---

## `date` Command

The `date` command print the current *date* and *time* on the standard output, and can further be set

	$ date 
	Thu Jun 30 19:42:15 EAT 2016

	# date --set='30 june 2016 13:57'
	Thu Jun 30 13:57:00 EAT 2016
	
**Note:** This Command will be very use-full in scripting, time and date based scripting, to be more precise.You also need to be root as thw command makes system wide changes.

---

## `cp` copy command

 It copies a file from one location to another location.
	
	$ cp /home/daumie/Downloads/file.txt /home/daumie/Desktop/

**Note:** `cp` is one of the most commonly used command in shell scripting and it can be used with wildcard characters _Describe in the above block_, for customised and desired file copying.

---

## `mv` Command

The `mv` move command moves files from one location to another

	$ mv /home/daumie/Downloads/file.txt /home/daumie/Desktop/

**Note:** `mv` command can be used with wildcard characters. `mv` should be used with caution, as moving of _system/unauthorised`_ file may lead to security issues as well as system breakdown. 

## `apropos` command

Sometimes you forget the name of a command but you know what it does. This command looks through all the help files and finds potentially relevant help for you.

	$ apropos search
	$ apropos find
	$ apropos remove
	$ apropos directory

Honestly, I only use this out of desperation. I first go search online and can usually find a better page describing what I want to do. If I still can't figure out what the name of that command was then I go through this help list until I see it.

## `pushd`  push directory and `popd`

You're getting into programmer territory with these commands, but they're so handy I have to teach them to you. These commands let you temporarily go to a different directory and then come back, easily switching between the two.

The `pushd` command takes your current directory and _pushes_ it into a list for later, then it changes to another directory. It's like saying, _Save where I am, then go here._

The `popd` command takes the last directory you pushed and _pops_ it off, taking you back there.

Finally, on Unix `pushd`, if you run it by itself with no arguments, will switch between your current directory and the last one you pushed.

These commands will surely make you comfortable with Linux. But it’s not the end. Very soon I will be coming with other commands which will be useful for _Middle Level User_

