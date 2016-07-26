---
layout: post
title: Load Average Explained
date:   2016-07-25 10:50:39  
categories: linux
---

- A frequently asked question in my classroom is “What is the meaning of load average and when is it too high?”.

 The one of the most important task of any Linux Admin includes <u>performance monitoring</u> which includes a parameter *load average* or *CPU Load*.

- Load Average is the value which represents the load on your system for a specific period of time. Also it can be considered the ratio of the number of active tasks to the number of available CPUs.

## How to check?

- To begin with Obtaining the current load average is very simple by issuing the `uptime` command or the `top` command.

#### `top` Command output.

The  `top`  program provides a dynamic real-time view of a running system.  It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel.
 
![top](/assets/img/top.png)

#### `uptime` Command output.

`uptime`  gives  a  one  line display of the following information.  The current time, how long the system has been running, how many users are currently logged on, and the system load averages for the past 1, 5, and 15 minutes.

![uptime](/assets/img/uptime.png)

#### `w` Command output.

 `w` displays information about the users currently on the machine, and their processes.  The header shows, in this order, the current time, how long the system has been running, how many users are currently logged on, and the system load averages for the past 1, 5, and 15 minutes.


![w](/assets/img/w.png)

#### What are the three values?

Interpreting the Load Average Output is quite simple.

>Basically load average is the run-queue utilization averaged over the *last minute*, the *last 5 minutes* and the *last 15 minutes*. The run-queue is a list of processes waiting for a resource to become available inside the Linux operating system. The example above from `uptime` command indicates that on average there were 1.07 processes waiting to be scheduled on the run-queue measured over the last minute.

From left to right the output gives the load average on the server for the last *1 minute*, *5 minutes* and *15 minutes*. For clarity, the load average for the above `uptime` output is explained below.

load average over the last 1 minute: _1.07_ 

load average over the last 5 minutes: _0.93_ 

load average over the last 15 minutes: _0.76_

### What information these numbers have?

The load average calculation varies when you have more CPU’s for your system, let’s assume that you have a single CPU, I am taking the above example itself to explain these numbers.

`over the last 1 minute: The CPU overloaded by 7%, On average .7 processes were waiting for the CPU. (1.07)`

`over the last 5 minutes: The CPU was idled for 7% of the time on average(0.93)`

`over the last 15 minutes: The CPU was idled for 24% of the time (0.76)`

---

You can simply calculate these with the below formula

**CPU overload = Average load – 1**

Example: Assume that the load is 4 on the system, then **CPU overload = 4-1** which gives you **3**, so **300%** overload. 

If you are getting a negative value for this, then the CPU has idle time (**CPU overload 0.93-1= -0.07*, which means 7% idle). 

---

## Load average on systems with multiple CPU’s

In a system with multiple CPU’s, these math will not do the trick. For example if we have load average 2 on a single CPU system, the *CPU overload is 2-1 = 100%*. Assume that you have 2 CPU’s, then the load handled by the CPU is its complete usage, you have to calculate it as *2-2 = 0%*. two different processes were using two different CPUs the entire time. On a system with four CPUs, this would be half usage — two processes were using two CPUs, while two CPUs were sitting idle.

So in general, we can say we need to know the number of CPU’s possessed by the system. Load average is very useful in the server environment, it helps in performance evaluation. If the load goes high, we may have to think about adding more resources to the system or optimize/terminate applications or processes  wasting resources. 
