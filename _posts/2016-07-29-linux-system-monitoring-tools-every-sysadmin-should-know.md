---
layout: post
title: Linux Sytem Monitoring Tools (PART 1)
date:   2016-07-29 08:50:39  
categories: sysadmin
---

Hello guys I know it’s hard work *monitoring* and *debugging* Linux performance problems, but it’s easier with the *right tools* at the *right time*. If you administer a Linux server, you'll want tools at the ready to help keep that baby humming. Some of these tools, such as a network traffic monitor, should be considered necessities. 

The commands discussed in the following sections are some of the most basic commands when it comes to system analysis and debugging server issues such as:

- Finding out bottlenecks.
- Disk (storage) bottlenecks.
- CPU and memory bottlenecks.
- Network bottlenecks.

To my knowledge here’s the most comprehensive list of Linux Monitoring Tools I have managed to compile.

For clarity , I will divide the tools into 5 categories:
- Command Line (**CLI**) tools
- Desktop Monitoring
- Infrastructure Monitoring
- Log Monitoring Tools
- Network Monitoring

---

## Command Line Tools

### `dstat`
`dstat` gives you detailed selective information in columns and clearly indicates in what magnitude and unit the output is displayed. Less confusion, less mistakes. And most importantly, it makes it very easy to write plugins to collect your own counters and extend in ways you never expected.

Dstat’s output by default is designed for being interpreted by humans in real-time, however you can export details to *CSV* output to a file to be imported later into Gnumeric or Excel to generate graphs. 

![dstat](/assets/img/command_line_tools/dstat.png)

---

### `top`

This is a small tool which is pre-installed on many unix systems. When you want an overview of all the processes or threads running in the system: top is a good tool. Order processes on different criteria – the default of which is CPU.
![top](/assets/img/command_line_tools/top.png)

---

### `htop`
`htop` is essentially an enhanced version of top. It’s easier to sort by processes. It’s visually easier to understand and has built in commands for common things you would like to do. Plus it’s fully interactive.
![htop](/assets/img/command_line_tools/htop.png)

---

### `atop`
`atop` monitors all processes much like top and htop, unlike top and htop however it has daily logging of the processes for long-term analysis. It also shows resource consumption by all processes. It will also highlight resources that have reached a critical load.
![atop](/assets/img/command_line_tools/atop.png)

---

### `apachetop`
`apachetop` monitors the overall performance of your apache webserver. It’s largely based on mytop. It displays current number of reads, writes and the overall number of requests processed.
![apachetop](/assets/img/command_line_tools/apachetop.png)

---

### `ftptop`
`ftptop` gives you basic information of all the current ftp connections to your server such as the total amount of sessions, how many are uploading and downloading and who the client is.

	# apt-get install proftpd-basic  

![ftptop](/assets/img/command_line_tools/ftptop.png)

---

### `mytop`
`mytop` is a neat tool for monitoring threads and performance of mysql. It gives you a live look into the database and what queries it’s processing in real time

![mytop](/assets/img/command_line_tools/mytop.png)

---

### `powertop`
`powertop` helps you diagnose issues that has to do with power consumption and power management. It can also help you experiment with power management settings to achieve the most efficient settings for your server.*Quickhint* You switch tabs with the tab key.

![powertop](/assets/img/command_line_tools/powertop.png)

---

### `iotop`
`iotop` checks the I/O usage information and gives you a top-like interface to that. It displays columns on read and write and each row represents a process. It also displays the percentage of time the process spent while swapping in and while waiting on I/O.

	 
![iotop](/assets/img/command_line_tools/iotop.png)

--- 
