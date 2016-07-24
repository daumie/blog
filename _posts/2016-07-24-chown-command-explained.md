---
layout: post
title: chown Command Explained
date:   2016-07-23 10:50:39  
categories: linux
---

`chown` is a command to change the ownership of a *file/folder* or even multiple *files/folders* at a time to a specified user/group. **CHOWN** stands for **CH**ange file **OWN**ership of _Owner_ and/or _Group_

---

How do I use `chmod` and `chown` command under Linux / Unix operating systems?

**Simple Answer:**

- Use the chown command to change file owner and group information.

- Use the chmod command to change file access permissions such as read, write, and access.

---

## `chown` Syntax

You can use `man` command to get full details about `chown` command.

	$ man chown

But in a nutshell: 

	chown owner-user path/to/file
	chown owner-user:owner-group path/to/file
	chown owner-user:owner-group directory
	chown options owner-user:owner-group path/to/file

---

I strongly believe learning through examples is good way to understand many things.

**Example 1:** How can I make daumie as the owner of the file?

	$ chown daumie file

In the above command the group owner will not be changed.

**Example 2:**How can I change ownership of multiple files to juser 'daumie'?

	$ chown daumie /path/to/file1 /path/to/file2 /path/to/file3

or

	$ chown daumie /path/to/{file1, file2, file3}

**Example 3:** How do I change the owner and group to daumie and students respectively?

	$ chown daumie:students

or 

	$ chown daumie.students 

**_Note_** : `.` And `:` are interchangeable.

**Example 4:** How about to change owner and group permissions where I know only their *UID* and *GID*?. 



Use those **UID** and **GID** in place of new owner and group

	$ chown 625:674 file1

Here user **UID** is *625* and **GID** of the new group is *674*.

**Example 5:** How to change ownership to daumie and group to user’s(_daumie_) primary group.

	$ chown daumie. File1

**Note:**Here you did not given group name after `.` so `chown` command will take primary group of the user in this case `daumie`.


**Example 6:** How do I change only group permissions to group `students` ? 

	$ chown .students file1

**Example 7:** How do I change a folder and its content to `daumie` ownership/group?

	$chown -R daumie:daumie /path/to/directory

**Example 8:** How do I change the ownership permissions *forcefully/silent/quiet* and don’t print any error?

	$chown -f daumie /path/to/file1

**Note :** We can mix up `-R` and `-f` options whenever required.

**Example 9:** I have a file located in `/home/user1/testfile` , now my requirement is I want the same ownership of this file to my second file which is located in `/var/ftp/file2`, how can I do it with out knowing the owner of that file?

Use `reference` option for this as shown below..

	$ chown –reference=/home/user1/testfile /var/ftp/file2

**Example 10:** How about changing all the files owned by *user:darius* in /var folder with new *employee:amos* joined as replacement of *khapwondi*?. Use `–from` option on that folder as shown below.

	$ chown –from=terry rob /var/*

#### Some rarely used options..

`c` – Show verbose output only when a change is made.

`v` – Show verbose output for every file processed.

---

<u>**Caution:**</u>

1.Be carefull when using chown command. See below two examples..

	chown user1:group1 / var/ftp

and

	chown user1:group1 /var/ftp

**Any difference you find between two commands?**
Yes, there is slight difference if you see first command there is a space between `/` and `var/ftp`. This is very dangerous mistake which will change entire file-system owner to `user1`

2.Some times there will be user called `nobody` as the owner of some files _(This is caused when an user account is deleted with out deleting his files/folders)_, at this time `chown` command will behave differently.Use `deluser` command when deleting a user so that these type of files will not be created or use `find` command to find all these type of files and change the ownership to new owner.

3.Sometimes you will *Operation not permitted* and *Permission Denied*, at this time please check if you are the owner of the file or not?
