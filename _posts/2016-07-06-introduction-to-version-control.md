---
layout: post
title: What Is Version Control?
date:   2016-07-06 15:50:39  
categories: git
---

---

A **Version Control Sytem _(VCS)_**  (also known as a _Revision Control Syystem_) is a repository of files, often the files for the source code of computer programs, with *monitored access*. Every change made to the source is tracked, along with who made the change, why they made it, and references to problems fixed, or enhancements introduced, by the change.

---

## Why Use a Version Control System?

If you’ve ever collaborated with other people on a project, you know the frustration of constantly swapping files. Some do it by email, some through file upload services and some by other methods. It’s a pain in the neck, and every designer and developer knows it. Revision control is an excellent way to combat the problem of sharing files between workers.

### Version Tracking

Developers may wish to compare today’s version of some software with yesterday’s version or last year’s version. Since version control systems keep track of every version of the software, this becomes a straightforward task. Knowing the what, who, and when of changes will help with comparing the performance of particular versions, working out when bugs were introduced (or fixed), and so on. Any problems that arose from a change can then be followed up by an examination of who made the change and the reasons they gave for making the change.

### Coordinating Teams

Resource development is usually carried out by teams, either co-located or distributed. Version control is central to coordinating teams of contributors. It lets one contributor work on a copy of the resources and then release their changes back to the common core when ready. Other contributors work on their own copies of the same resources at the same time, unaffected by each other’s changes until they choose to merge or commit their changes back to the project

### Due Diligence

 A version control system provides a means for monitoring those changes as they occur. Automated systems will notify those responsible for managing the IP in project outputs. These notifications, coupled with the logs provided for each individual modification, allow project managers to monitor and trace all contributions.

## Types of Version Control Systems

The two most popular version control systems are broken down into two main categories :
	
	centralized

	distributed (also known as decentralized)

## Centralized Version Control
![cvc](/blog/assets/img/cvc.png)

---

Centralized version control systems are based on the idea that there is a single “central” copy of your project somewhere (probably on a server), and programmers will “commit” their changes to this central copy.


When you’re working with a centralized verison control system, your workflow for adding a new feature or fixing a bug in your project will usually look something like this:

- Pull down any changes other people have made from the central server.

- Make your changes, and make sure they work properly.

- Commit your changes to the central server, so other programmers can see them

Some of the most common centralized version control systems you may have heard of or used are *CVS*, *Subversion (or SVN)* and *Perforce*.

---

## Distributed Version Control

Distributed systems are a newer option. In distributed version control, each user has their own copy of the entire repository, not just the files but the history as well.

![cvc](/blog/assets/img/dvc.png)

---

 Think of it as a network of individual repositories. In many cases, even though the model is distributed, services like Beanstalk are used for simplifying the technical challenges of sharing changes. The two most popular distributed version control systems are *Git* and *Mercurial*. 
 The primary benefits of Git and Mercurial are:

- More powerful and detailed change tracking, which means less conflicts.

- No server necessary – all actions except sharing repositories are local (commit offline).

- Branching and merging is more reliable, and therefore used more often.

- It’s fast.

### Advantages Over Centralized Version Control

The act of cloning an entire repository gives distributed version control tools several advantages over centralized systems:

- Performing actions other than pushing and pulling changesets is extremely fast because the tool only needs to access the hard drive, not a remote server.

- Committing new changesets can be done locally without anyone else seeing them. Once you have a group of changesets ready, you can push all of them at once.

- Everything but pushing and pulling can be done without an internet connection. So you can work on a plane, and you won’t be forced to commit several bugfixes as one big changeset.

- Since each programmer has a full copy of the project repository, they can share changes with one or two other people at a time if they want to get some feedback before showing the changes to everyone.


## Further Reading


- [Github](https://github.com/)
- [SourceForge)](http://sourceforge.net/)
- [Google Code)](http://code.google.com/)
- [Git (open source)](http://git-scm.com/)
- [CVS (open source)](http://www.nongnu.org/cvs/)
- [Arch (open source)](http://www.gnu.org/software/gnu-arch/)
- [Subversion (open source)](http://subversion.apache.org/)
- [BitKeeper](http://www.bitkeeper.com/)
- [Perforce](http://www.perforce.com/)
- [AccuRev](http://www.accurev.com/accurev-version-control.html)
- [Visual (Source Safe) ](http://www.microsoft.com/vstudio/previous/ssafe/)




