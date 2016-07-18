---
layout: post
title: 4 ways to identify who is logged-in in your linux system.
date:   2016-07-19 08:50:39  
categories: linux
---

As a system administrator, you may want to know who is on the system at any give point in time. You may also want to know what they are doing. In this article let us review 4 different methods to identify who is on your Linux system.

## 1. Get the running processes of logged-in user using w

`w` command is used to show logged-in user names and what they are doing. The information will be read from `/var/run/utmp` file. The output of the `w`command contains the following columns:


- Name of the user
- User’s machine number or tty number
- Remote machine address
- User’s Login time
- Idle time (not usable time)
- Time used by all processes attached to the tty (JCPU time)
- Time used by the current process (PCPU time)
- Command currently getting executed by the users

 
### Following options can be used for the `w` command:

- `h` Ignore the header information
- `u` Display the load average (uptime output)
- `s` Remove the JCPU, PCPU, and login time.

---


	$ w
	00:14:31 up 1 day, 15:52,  3 users,  load average: 0.25, 0.46, 0.48
	USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
	daumie   tty7     :0               Sun08   39:52m  1:52m  5.80s /sbin/upstart --user
	daumie   pts/21   tmux(23643).%0   19:30    4:38m  0.42s  0.08s ssh signup@ssh.blinkenshell.org -p 443
	daumie   tty2                      00:00   12:55   0.41s  0.37s -zsh
	
	$ w -h
	daumie   tty7     :0               Sun08   39:55m  1:52m  5.82s /sbin/upstart --user
	daumie   pts/21   tmux(23643).%0   19:30    4:41m  0.42s  0.08s ssh signup@ssh.blinkenshell.org -p 443
	daumie   tty2                      00:00   15:54   0.41s  0.37s -zsh

	$ w -u 
	00:18:34 up 1 day, 15:56,  3 users,  load average: 0.87, 0.51, 0.48
	USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
	daumie   tty7     :0               Sun08   39:56m  1:52m  5.82s /sbin/upstart --user
	daumie   pts/21   tmux(23643).%0   19:30    4:42m  0.42s  0.08s ssh signup@ssh.blinkenshell.org -p 443
	daumie   tty2                      00:00   16:58   0.41s  0.37s -zsh

	$ w -s 
	00:19:45 up 1 day, 15:57,  3 users,  load average: 1.07, 0.62, 0.51
	USER     TTY      FROM              IDLE WHAT
	daumie   tty7     :0               39:57m /sbin/upstart --user
	daumie   pts/21   tmux(23643).%0    4:43m ssh signup@ssh.blinkenshell.org -p 443
	daumie   tty2                      18:09  -zsh

---	

## 2. Get the user name and process of logged in user using who and users command

`who` command is used to get the list of the usernames who are currently logged in. Output of the who command contains the following columns: user name, tty number, date and time, machine address.

	daumie   tty7         2016-07-17 08:24 (:0)
	daumie   pts/21       2016-07-18 19:30 (tmux(23643).%0)
	daumie   tty2         2016-07-19 00:00

To get a list of all usernames that are currently logged in, use the following:

	$ who | cut -d' ' -f1 | sort | uniq
	daumie

### `users` Command

`users` command is used to print the user name who are all currently logged in the current host. It is one of the command don’t have any option other than help and version. If the user using, **n** number of terminals, the user name will shown in **n** number of time in the output.

	$ users 
	daumie daumie daumie

### 3. Get the username you are currently logged in using `whoami`

`whoami` command is used to print the loggedin user name.

	$ whoami 
	daumie 

`whoami` command gives the same output as `id -un` as shown below: 

	$ id -un 
	daumie

	$  who mom likes 
	daumie 

Warning: **Don't try** `who mom hates` command  :-)

### 4. Get the user login history at any time using last command

`last` command will give login history for a specific username. If we don’t give any argument for this command, it will list login history for all users. By default this information will read from `/var/log/wtmp` file. The output of this command contains the following columns:

- User name
- Tty device number
- Login date and time
- Logout time
- Total working time

---

	$ last daumie
	daumie   pts/18       tmux(23643).%1   Tue Jul 19 00:15 - 00:15  (00:00)
	daumie   tty2                          Tue Jul 19 00:00   still logged in
	daumie   pts/21       tmux(23643).%0   Mon Jul 18 19:30    gone - no logout
	daumie   tty1                          Mon Jul 18 16:56 - 23:58  (07:02)
	daumie   tty7         :0               Sun Jul 17 08:24    gone - no logout
	daumie   tty7         :0               Sat Jul 16 19:51 - down   (04:21)
	daumie   tty2                          Fri Jul 15 22:28 - crash  (21:21)
	daumie   tty1                          Fri Jul 15 22:27 - crash  (21:22)
	daumie   tty7         :0               Fri Jul 15 16:37 - crash (1+03:11)
	daumie   tty7         :0               Fri Jul 15 13:03 - down   (03:33)
	daumie   tty7         :0               Thu Jul 14 12:35 - crash (1+00:26)
	daumie   tty7         :0               Wed Jul 13 12:44 - crash  (23:50)
	daumie   tty1                          Mon Jul 11 10:23 - 19:26  (09:03)
	daumie   tty7         :0               Mon Jul 11 08:46 - crash (2+03:56)
	daumie   tty2                          Mon Jul 11 00:41 - down   (00:11)
	daumie   pts/21       tmux(22859).%0   Sun Jul 10 17:38 - 17:39  (00:00)
	daumie   pts/21       tmux(22157).%0   Sun Jul 10 17:03 - 17:03  (00:00)
	daumie   tty1                          Sun Jul 10 15:26 - down   (09:25)
	daumie   tty2                          Sun Jul 10 15:25 - 21:25  (05:59)
	daumie   tty7         :0               Sat Jul  9 08:49 - down  (1+16:03)
	daumie   tty7         :0               Sat Jul  9 00:16 - down   (00:01)
	daumie   tty7         :0               Thu Jul  7 09:13 - down  (1+14:58)
	daumie   tty7         :0               Wed Jul  6 23:25 - down   (01:38)
    daumie   tty2                          Wed Jul  6 23:23 - crash  (00:01                                                        daumie   tty7         :0               Wed Jul  6 16:37 - crash  (06:47                                                        daumie   tty7         :0               Tue Jul  5 17:51 - crash  (22:41                                                        daumie   tty7         :0               Tue Jul  5 09:17 - crash  (08:32                                                        daumie   tty7         :0               Mon Jul  4 16:41 - down   (09:10                                                        daumie   tty7         :0               Mon Jul  4 00:25 - crash  (16:06                                                    daumie   tty7         :0               Sat Jul  2 15:43 - down  (1+06:15)
