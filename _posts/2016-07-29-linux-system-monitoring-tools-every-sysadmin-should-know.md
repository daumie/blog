---
layout: post
title: Linux Sytem Monitoring Tools Every Sytem Admin Should Know
date:   2016-07-29 08:50:39  
categories: sysadmin
---

Hello guys I know it’s hard work *monitoring* and *debugging* Linux performance problems, but it’s easier with the *right tools* at the *right time*. 
To my knowledge here’s the most comprehensive list of Linux Monitoring Tools I have managed to compile.

For clarity , I will divide the tools into 5 categories:
- Command Line (**CLI**) tools
- Desktop Monitoring
- Infrastructure Monitoring
- Log Monitoring Tools
- Network Monitoring

---

## Command Line Tools

### `top`

This is a small tool which is pre-installed on many unix systems. When you want an overview of all the processes or threads running in the system: top is a good tool. Order processes on different criteria – the default of which is CPU.
![top](/assets/img/top.png)

---

### `htop`
`htop` is essentially an enhanced version of top. It’s easier to sort by processes. It’s visually easier to understand and has built in commands for common things you would like to do. Plus it’s fully interactive.
![htop](/assets/img/htop.png)

---

### `atop`
`atop` monitors all processes much like top and htop, unlike top and htop however it has daily logging of the processes for long-term analysis. It also shows resource consumption by all processes. It will also highlight resources that have reached a critical load.
![atop](/assets/img/atop.png)

---

### `apachetop`
`apachetop` monitors the overall performance of your apache webserver. It’s largely based on mytop. It displays current number of reads, writes and the overall number of requests processed.
![apachetop](/assets/img/apachetop.png)

---

### `ftptop`
`ftptop` gives you basic information of all the current ftp connections to your server such as the total amount of sessions, how many are uploading and downloading and who the client is.

	# apt-get install proftpd-basic  

![ftptop](/assets/img/ftptop.png)

---

### `mytop`
`mytop` is a neat tool for monitoring threads and performance of mysql. It gives you a live look into the database and what queries it’s processing in real time

![mytop](/assets/img/mytop.png)

---

### `powertop`
`powertop` helps you diagnose issues that has to do with power consumption and power management. It can also help you experiment with power management settings to achieve the most efficient settings for your server.*Quickhint* You switch tabs with the tab key.

![powertop](/assets/img/powertop.png)

---

### `iotop`
`iotop` checks the I/O usage information and gives you a top-like interface to that. It displays columns on read and write and each row represents a process. It also displays the percentage of time the process spent while swapping in and while waiting on I/O.

	 
![iotop](/assets/img/iotop.png)

---

## Desktop Monitoring

### `ntopng`
`ntopng` is the next generation of ntop and the tool provides a graphical user interface via the browser for network monitoring. It can do stuff such as: geolocate hosts, get network traffic and show ip traffic distribution and analyze it.

![ntopng](/assets/img/ntopng.png)

---

### `iftop`
`iftop` is similar to `top`, but instead of mainly checking for cpu usage it listens to network traffic on selected network interfaces and displays a table of current usage. It can be handy for answering questions such as *“Why on earth is my internet connection so slow?!”.*

	
![iftop](/assets/img/iftop.png)

---

### `jnettop`
`jnettop` visualises network traffic in much the same way as iftop does. It also supports customizable text output and a machine-friendly mode to support further analysis.

![jnettop](/assets/img/jnettop.png)

---

### `bandwidthd`
`bandwidthd` tracks usage of *TCP/IP* network subnets and visualises that in the browser by building a html page with graphs in png. There is a database driven system that supports searching, filtering, multiple sensors and custom reports.
![bandwidthd](/assets/img/bandwidthd.png)