---
layout: post
title: Linux Sytem Monitoring Tools Every Sytem Admin Should Know (PART 2)
date:   2016-07-30 08:50:39  
categories: sysadmin
---
This is part 2 of the linux system montiring tools.I'm going to rant about `desktop monitoring`  tools 

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

---

### `etherape`
`etherape` displays network traffic graphically, the more talkative the bigger the node. It either captures live traffic or can read it from a `tcpdump`. The displayed can also be refined using a network filter with `pcap` syntax.

![etherape](/assets/img/etherape.png)

---

### ethtool
`ethtool` is used for displaying and modifying some parameters of the network interface controllers. It can also be used to diagnose Ethernet devices and get more statistics from the devices.

![ethtool](/assets/img/ethtool.png)

---

### `nethogs`
`nethogs` breaks down network traffic per protocol or per subnet. It then groups by process. So if there’s a surge in network traffic you can fire up NetHogs and see which process is causing it.

![nethogs](/assets/img/nethogs.png)

---

### `iptraf`
`iptraf` gathers a variety of metrics such as TCP connection packet and byte count, interface statistics and activity indicators, TCP/UDP traffic breakdowns and station packet and byte counts.

![iptraf](/assets/img/iptraf.png)

---

### `ngrep`
`ngrep`  strives to provide most of GNU grep's common features, applying them to the network layer.  ngrep is a pcap-aware tool that will  allow you to specify extended regular expressions to match against data payloads of packets.  It currently recognizes TCP, UDP and ICMP across Ethernet, PPP, SLIP, FDDI and null interfaces, and understands bpf filter logic in the same fashion as more common packet sniffing  tools,  such as tcpdump(8) and snoop(1).

![ngrep](/assets/img/ngrep.png)

----

### `mrtg`

The `Multi Router Traffic Grapher (MRTG)` is a tool to monitor the traffic load on network links.  `MRTG` generates `HTML` pages containing PNG images which provide a LIVE visual representation of this traffic. Check out the [official site](http://www.stat.ee.ethz.ch/mrtg/) to see what it does.It typically collects every five minutes and then generates a html page. It also has the capability of sending warning emails.

![mrtg](/assets/img/mrtg.png)

----