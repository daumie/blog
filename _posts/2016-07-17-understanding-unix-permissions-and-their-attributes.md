---
layout: post
title: Understanding UNIX permissions and their attributes
date:   2016-07-17 10:50:39  
categories: linux
---


I've never really got how `chmod` worked up until today. I followed a tutorial that explained a big deal to me.

The chmod command in Linux/Unix is abbreviated as **CH**ange  **MOD**e. Chmod command is useful to change permission for Files and folders in Linux/Unix. 

This type of restriction is useful for effective file/folder management, securing system and providing a level of access to a file/folder for the users who access them.

![Chmod](/assets/img/chmod.png)

For example, I've read that you've got three different permission groups._(For every file we define 3 sets of people for whom we may specify permissions.)_

- owner **(u)**  - a single person who owns the file. (typically the person who created the file but ownership may be granted to some one else by certain users)
- group **(g)**  - every file belongs to a single group.
- everyone **(o)**  - everyone else who is not in the group or the owner.

To view permissions for a file we use the long listing option for the command ls.

	$ ls -l
	
Based on these three groups, I now know that:

- If the file is owned by the user, the user permissions determine the access.
- If the group of the file is the same as the user's group, the group permisson determien the access.
- If the user is not the file owner, and is not in the group, then the other permission is used.

I've also learned that you've got the following **3** permissions to rule them all:

- read **(r)** - you may view the contents of the file.
- write **(w)** - you may change the contents of the file.
- execute **(x)** - you may execute or run the file if it is a program or script.

---

## How can we change permissions for a file/directory?

Permission/access is either Executable or Writable or Readable for a file/folder and can be changed by using following methods

1. Numerical method: Specifying numbers **(1, 2, and 4,)** to change the permission for a file/folder

2. Alpha method: Using alphabets **(w, x, r, u, o, g, a, -, +, =, s, t)** to change permissions for a file/folder

---

### Numerical method

    2^0=1 --eXecute

    2^1=2 --Write

    2^2=4 --Read 

Addition to this there are three more concepts which are linked to this numbering method **(I SUID, SGID, Sticky Bit)**. I will explain about these things in coming posts. 

---

## Alpha Method

`w` --Write

`x` --eXecute

`r` --Read

`u` --User

`g` --Group

`o` --Others

`a` --all

`+` --Add specified permissions to the mention user/group/others/all

`-` --Remove specified permissions from the mention user/group/others/all

`=` --Replicate the permission to other class of the group/user/others.

Addition to these there are **s** and **t** permissions_(SUID, SGID and Sticky Bit)_ available for chmod command which we will discuss in next chmod tutorial. 

---

### file types

The first character identifies the file type. If it is a dash `( - )` then it is a normal file. If it is a `d` then it is a directory. It can't be set or unset, it depends on how the file was created. You can find the complete list of file types in the [ls documentation](http://www.gnu.org/software/coreutils/manual/html_node/What-information-is-listed.html#What-information-is-listed); those you're likely to come across are

- `-` : "regular" file, created with any program which can write a file
- `b` : block special file, typically disk or partition devices, can be created with mknod
- `c` : character special file, can also be created with mknod (see /dev for examples)
- `d` : directory, can be created with mkdir
- `l` : symbolic link, can be created with ln -s
- `p` : named pipe, can be created with mkfifo
- `s` : socket, can be created with nc -U
- `D` : door, created by some server processes on Solaris/openindiana.

---

## Example

	┌─[daumie@casper] - [~/Pictures] - [Sun Jul 17, 07:40]
	└─[$] <> ls -l
	total 9124
	-rw-rw-r-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

As we said :

- The first character identifies the file type. If it is a dash `( - )` then it is a normal file. If it is a `d` then it is a directory.

- The following 3 characters represent the persmissions for the **owner**. A letter represents the presence of a permission and a dash `( - )` represents the absence of a permission. In this example the owner has two permissions (*read* and *write*).

- The following 3 characters represent the permissions for the **group**. In this example the group has the ability to *read* , *write* but not *execute*. Note that the order of permissions is always <u>read</u> , then <u>write</u> then <u>execute</u>.

- Finally the last 3 characters represent the permissions for **others** _(or everyone else)_. In this example they have the *read* permission and nothing else.

## Change Permissions

**chmod** has permission arguments that are made up of 3 components


- Who are we changing the permission for? [**ugoa**] - user (or **owner**), **group**, **others**, **all**
- Are we granting or revoking the permission - indicated with either a plus ( + ) or minus ( - )
- Which permission are we setting? - read ( **r** ), write ( **w** ) or execute ( **x** )

The following examples will make their usage clearer.

Grant the execute permission to the group. Then remove the write permission for the owner.

##### grant the execute permission to the group.

	daumie@casper $ ls -l lantern.jpg
	-rw-rw-r-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

	daumie@casper $ chmod g+x lantern.jpg 

	daumie@casper $ ls -l 
	-rw-rwxr-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

---

##### remove the write permission for the owner (_user_)

	daumie@casper $ ls -l lantern.jpg 
	-rw-rwxr-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

	daumie@casper $ chmod u-w lantern.jpg 

	daumie@casper $ ls -l lantern.jpg
	-r--rwxr-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

---

Don't want to assign permissions individually? We can assign multiple permissions at once

	daumie@casper $ ls -l lantern.jpg
	-r--rwxr-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

	daumie@casper $ chmod u+wx lantern.jpg

	daumie@casper $ ls -l lantern.jpg
	-rwxrwxr-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

---

	daumie@casper $ chmod gu-r lantern.jpg 

	daumie@casper $ ls -l lantern.jpg 
	--wx-wxr-- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

---

It may seem odd that as the owner of a file we can remove our ability to read, write and execute that file but there are valid reasons we may wish to do this. Maybe we have a file with data in it we wish not to accidentally change for instance. While we may remove these permissions, we may not remove our ability to set those permissions and as such we always have control over every file under our ownership.

---

### Setting Permissions Shorthand

The method outlined above is not too hard for setting permissions but it can be a little tedious if we have a specific set of permissions we sould like to apply regularly to certain files. Luckily, there is a shorthand way to specify permissions that makes this easy.

To understand how this shorthand method works we first need a little background in number systems. Our typical number system is decimal. It is a *base 10 number* system and as such has 10 symbols _(0 - 9)_ used. Another number system is *octal* which is base 8 _(0-7)_. Now it just so happens that with 3 permissions and each being on or off, we have 8 possible combinations _(2^3)_. Now we can also represent our numbers using binary which only has 2 symbols _(0 and 1)_. The mapping of octal to binary is in the table below.

| **<u>Octal</u>** | **<u>Binary</u>** |
| :---: | :---: |
| **0**  | `0 0 0` |
| **1**  | `0 0 1` |
| **2**  | `0 1 0` |
| **3**  | `0 1 1` |
| **4**  | `1 0 0` |
| **5**  | `1 0 1` |
| **6**  | `1 1 0` |
| **7**  | `1 1 1` |

To learn more about binary numbers check out our [Binary Tutorial](#)

---

Now the interesting point to note is that we may represent all 8 octal values with 3 binary bits and that every possible combination of 1 and 0 is included in it. So we have 3 bits and we also have 3 permissions. If you think of 1 as representing on and 0 as off then a single octal number may be used to represent a set of permissions for a set of people. Three numbers and we can specify permissions for the user, group and others. Let's see some examples. _(refer to the table above to see how they match)_

	daumie@casper $ls -l lantern.jpg
	-rw-r----x 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

	daumie@casper $ chmod 751 lantern.jpg 

	daumie@casper $ls -l lantern.jpg
	-rwxr-x--x 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg

	daumie@casper $ chmod 240 lantern.jpg 

	daumie@casper $ls -l lantern.jpg
	--w-r----- 1 daumie daumie 138058 Jul 10 22:04 lantern.jpg


## Examples

#### Through Numerical method

**Example 1**: The file should have read, write and execute permissions to user, read and execute permissions to group and read, and execute permissions to others.

read, write and execute permissions to user  = **7**

read and execute permissions to group  = **5**

read and execute permissions to others = **5**

So total permissions will be **755** 

	$ chmod 755 filename


**Example 2**: Providing write access to a user 

	$ chmod u+w filename

**Example 3**: Adding write permissions to a group 

	$ chmod g+w filename

**Example 4**: Adding executable permissions to others

	$ chmod o+x filename

**Example 5**: Adding executable and write permissions to all

	$ chmod a+wx filename

**Example 6**: Replicating user permissions to a group

	$ chmod u=g filename

**Example 7**: Removing execute permissions to a user

	$ Chmod u-x filename

**Example 8**: Adding execute permissions to others

	$ Chmod o+x
	
People often remember commonly used number sequences for different types of files and find this method quite convenient. For example **755** or **750** are commonly used for scripts.


### Permissions for Directories

The same series of permissions may be used for directories but they have a slightly different behaviour.

- **r** - you have the ability to read the contents of the directory (ie do an ls)
- **w** - you have the ability to write into the directory (ie create files and directories)
- **x** - you have the ability to enter that directory (ie cd)

Let's see some of these in action

	daumie@casper $ mkdir testdir
	daumie@casper $ touch file1 file2 file3
	daumie@casper $ echo "This are the names" >> file1
	daumie@casper $ chmod 400 testdir/ 
	daumie@casper @ ls -ld  testdir/ 
	dr-------- 2 daumie daumie 4096 Jul 17 21:50 testdir
	daumie@casper $ cd testdir 
	cd: permission denied: testdir

	daumie@casper $ ls testdir 
	ls: cannot access 'testdir/file3': Permission denied
	ls: cannot access 'testdir/file1': Permission denied
	ls: cannot access 'testdir/file2': Permission denied
	file1  file2  file3
	
	daumie@casper $ chmod 100 testdir
	daumie@casper $ ls -ld testdir 
	d--x------ 2 daumie daumie 4096 Jul 17 22:02 testdir

	daumie@casper $ cd testdir 
	daumie@casper $ ls testdir
	ls: cannot open directory '.': Permission denied

Note, on lines 3 and 14 above when we ran ls I included the -d option which stands for directory. Normally if we give ls an argument which is a directory it will list the contents of that directory. In this case however we are interested in the permissions of the directory directly and the `-d` option allows us to obtain that.

These permissions can seem a little confusing at first. What we need to remember is that these permissions are for the directory itself, not the files within. So, for example, you may have a directory which you don't have the read permission for. It may have files within it which you do have the read permission for. As long as you know the file exists and it's name you can still read the file.

	daumie@casper $ ls -ld testdir 
	d--x------ 2 daumie daumie 4096 Jul 17 22:10 testdir

	daumie@casper $ cd testdir 
	daumie@casper $ ls 
	s: cannot open directory '.': Permission denied
	
	daumie@casper$ cat file1 
	This are the names  

---

### The root user

On a Linux system there are only **2** people usually who may change the permissions of a file or directory. The owner of the file or directory and the root user. The **root** user is a <u>superuser who is allowed to do anything and everything on the system</u>. Typically the administrators of a system would be the only ones who have access to the root account and would use it to maintain the system. Typically normal users would mostly only have access to files and directories in their home directory and maybe a few others for the purposes of sharing and collaborating on work and this helps to maintain the security and stability of the system.

### Basic Security

Your home directory is your own personal space on the system. You should make sure that it stays that way.

Most users would give themselves full read, write and execute permissions for their home directory and no permissions for the group or others however some people for various reasons may have a slighly different set up.

Normally, for optimal security, you should not give either the group or others write access to your home directory, but execute without read can come in handy sometimes. This allows people to get into your home directory but not allow them to see what is there. An example of when this is used is for personal web pages.

It is typical for a system to run a webserver and allow users to each have their own web space. A common set up is that if you place a directory in your home directory called public_html then the webserver will read and display the contents of it. The webserver runs as a different user to you however so by default will not have access to get in and read those files. This is a situation where it is necessary to grant execute on your home directory so that the webserver user may access the required resources.

---

#### Summary - stuff we have learnt

`chmod`

 Change permissions on a file or directory.

`ls -ld`

 View the permissions for a specific directory.

---

#### Important concepts

- **Security**

    Correct permissions are important for the security of a system.

- **Usage**

    Setting the right permissions is important in the smooth running of certain tasks on Linux. (we will see an example of this in Section 13 on scripting)
    
### Activities

Let's play with some permissions.

- First off, take a look at the permissions of your home directory, then have a look at the permissions of various files in there.

- Now let's go into your linuxtutorialwork directory and change the permissions of some of the files in there. Make sure you use both the shorthand and longhand form for setting permissions and that you also use a variety of absolute and relative paths. Try removing the read permission from a file then reading it. Or removing the write permission and then opening it in vi.

- Let's play with directories now. Create a directory and put some files into it. Now play about with removing various permissions from yourself on that directory and see what you can and can't do.

- Finally, have an explore around the system and see what the general permissions are for files in other system directories such as /etc and /bin


