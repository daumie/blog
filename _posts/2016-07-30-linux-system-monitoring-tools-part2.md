---
layout: post
title: Desktop Monitoring (SysAdmin)
date:   2016-07-30 08:50:39  
categories: sysadmin
---
This is part 2 of the linux system montiring tools.I'm going to rant about `desktop monitoring`  tools 

## Desktop Monitoring

### `ntopng`
`ntopng` is the next generation of ntop and the tool provides a graphical user interface via the browser for network monitoring. It can do stuff such as: geolocate hosts, get network traffic and show ip traffic distribution and analyze it.

![ntopng](/assets/img/desktop_monitoring/ntopng.png)

---

### `iftop`
`iftop` is similar to `top`, but instead of mainly checking for cpu usage it listens to network traffic on selected network interfaces and displays a table of current usage. It can be handy for answering questions such as *“Why on earth is my internet connection so slow?!”.*

![iftop](/assets/img/desktop_monitoring/iftop.png)

---

### `jnettop`
`jnettop` visualises network traffic in much the same way as iftop does. It also supports customizable text output and a machine-friendly mode to support further analysis.

![jnettop](/assets/img/desktop_monitoring/jnettop.png)

---

### `bandwidthd`
`bandwidthd` tracks usage of *TCP/IP* network subnets and visualises that in the browser by building a html page with graphs in png. There is a database driven system that supports searching, filtering, multiple sensors and custom reports.

![bandwidthd](/assets/img/desktop_monitoring/bandwidthd.png)

---

### `etherape`
`etherape` displays network traffic graphically, the more talkative the bigger the node. It either captures live traffic or can read it from a `tcpdump`. The displayed can also be refined using a network filter with `pcap` syntax.

![etherape](/assets/img/desktop_monitoring/etherape.png)

---

### `ethtool`
`ethtool` is used for displaying and modifying some parameters of the network interface controllers. It can also be used to diagnose Ethernet devices and get more statistics from the devices.

![ethtool](/assets/img/desktop_monitoring/ethtool.png)

---

### `nethogs`
`nethogs` breaks down network traffic per protocol or per subnet. It then groups by process. So if there’s a surge in network traffic you can fire up NetHogs and see which process is causing it.

![nethogs](/assets/img/desktop_monitoring/nethogs.png)

---

### `iptraf`
`iptraf` gathers a variety of metrics such as TCP connection packet and byte count, interface statistics and activity indicators, TCP/UDP traffic breakdowns and station packet and byte counts.

![iptraf](/assets/img/desktop_monitoring/iptraf.png)

---

### `ngrep`
`ngrep`  strives to provide most of GNU grep's common features, applying them to the network layer.  ngrep is a pcap-aware tool that will  allow you to specify extended regular expressions to match against data payloads of packets.  It currently recognizes TCP, UDP and ICMP across Ethernet, PPP, SLIP, FDDI and null interfaces, and understands bpf filter logic in the same fashion as more common packet sniffing  tools,  such as tcpdump(8) and snoop(1).

![ngrep](/assets/img/desktop_monitoring/ngrep.png)

----

### `mrtg`

The `Multi Router Traffic Grapher (MRTG)` is a tool to monitor the traffic load on network links.  `MRTG` generates `HTML` pages containing PNG images which provide a LIVE visual representation of this traffic. Check out the [official site](http://www.stat.ee.ethz.ch/mrtg/) to see what it does.It typically collects every five minutes and then generates a html page. It also has the capability of sending warning emails.

![mrtg](/assets/img/desktop_monitoring/mrtg.png)

----

### `traceroute`
`traceroute`  tracks  the route packets taken from an IP network on their way to a given host. It utilizes the IP protocol's *time to live* (TTL) field and attempts to elicit an **ICMP TIME_EXCEEDED** response from each gateway along the path to the host.It's basically used  for displaying the route and measuring the delay of packets across a network.

![traceroute](/assets/img/desktop_monitoring/traceroute.png)

---

### `iptstate`
`IPTState` allows you to watch where traffic that crosses your iptables is going and then sort that by different criteria as you please. The tool also allows you to delete states from the table.
`iptstate`  displays  information  held  in  the IP Tables state table in real-time in a top-like format.  Output can be sorted by any field,  or any field reversed. Users can choose to have the output only print once and exit, rather than the top-like  system.  Refresh  rate  is  configurable, IPs can be resolved to names, output can be formatted, the display can be filtered, and color coding are among some of the many  features.

![iptstate](/assets/img/desktop_monitoring/iptstate.png)

---

#### `darkstate`
`darkstat` is a packet sniffer that runs as a background process, gathers all sorts of statistics about network usage,  and  serves  them  over **HTTP**.*All settings are passed on the commandline.*
Darkstat captures network traffic and calculates statistics about usage. The reports are served over a simple HTTP server and gives you a nice graphical user interface of the graphs.

![darkstat](/assets/img/desktop_monitoring/darkstat.png)

---

### `vnstat`
`vnStat` is a network traffic monitor that uses statistics provided by the kernel which ensures light use of system resources. The gathered statistics persists through system reboots. It has color options for the artistic sysadmins.

`vnStat` is a console-based network traffic monitor. It keeps a log of hourly, daily and monthly network traffic for the selected interface(s).However, it isn't a packet sniffer. The traffic information is read from the *proc(5)* or *sys* filesystems depending on availability.  That  way `vnStat` can be used even without root permissions on most systems.

The implementation is divided into two commands. The purpose of the `vnstat` command is to provide an interface for querying the traffic information stored in network interface specific databases where as the daemon *vnstatd(1)* is responsible for data retrieval and storage.  Althoughthe daemon process is constantly running as a service, it is actually spending most of the time sleeping between data updates.

![vnstat](/assets/img/desktop_monitoring/vnstat.png)

---

### `netstat`
`netstat` is a built-in tool that displays TCP network connections, routing tables and a number of network interfaces. It’s used to find problems in the network.

![netstat](/assets/img/desktop_monitoring/netstat.png)

---

### `ss`
Instead of using `netstat`, it’s however preferable to use ss. The `ss` command is capable of showing more information than netstat and is actually faster. If you want a summary statistics you can use the command `ss -s`.

![ss](/assets/img/desktop_monitoring/ss.png)

---

### `nmap`
`nmap` allows you to scan your server for open ports or detect which OS is being used. But you could also use this for SQL injection vulnerabilities, network discovery and other means related to penetration testing.

![nmap](/assets/img/desktop_monitoring/nmap.png)

---

### `mtr`
`MTR` combines the functionality of traceroute and the ping tool into a single network diagnostic tool. When using the tool it will limit the number hops individual packets has to travel while also listening to their expiry. It then repeats this every second.
It's worthy noting that the results  are  usually  reported  as  round-trip-response  times  in miliseconds and the percentage of packetloss.

![mtr](/assets/img/desktop_monitoring/mtr.png)

---

### `tcpdump`
`tcpdump` will output a description of the contents of the packet it just captured which matches the expression that you provided in the command. You can also save the this data for further analysis.

![tcpdump](/assets/img/desktop_monitoring/tcpdump.png)

---

### `justniffer`
`justniffer` is a tcp packet sniffer. You can choose whether you would like to collect low-level data or high-level data with this sniffer. It also allows you to generate logs in customizable way. You could for instance mimic the access log that apache has.

![justniffer](/assets/img/desktop_monitoring/justniffer.png)

---

### `bmon`
`bmon` is a monitoring and debugging tool to capture  networking  related statistics  and  prepare them visually in a human friendly way. It features various output  methods  including  an  interactive  curses  user interface and a programmable text output for scripting.

![bmon](/assets/img/desktop_monitoring/bmon.png)

---
