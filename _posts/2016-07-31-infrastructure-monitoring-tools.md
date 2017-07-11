---
layout: post
title: Infrastructure Monitoring Tools (SysAdmin)
date:   2016-07-31 08:50:39  
categories: sysadmin
---

### `opennms`
**OpenNMS** is a carrier-grade, highly integrated, open source platform designed for building network monitoring solutions. There are two distributions of OpenNMS: Meridian and Horizon. Using **Meridian** is advisable for *enterprises* and *businesses* looking for *stability* and *long term support*. **Horizon** is the place where *innovation* happens *quickly* and is ideal for monitoring new technologies and IT ecosystems. Both distributions are completely open source.
OpenNMS has four main functional areas.

- event management and notifications
- discovery and provisioning
- service monitoring and data collection 
- It’s designed to be customizable to work in a variety of network environments.

![opennms](/blog/assets/img/infrastructure_monitoring/opennms.png)

More info on the [opennms official site](http://www.opennms.org/en)

---

### `SysUsage`
`SysUsage` monitors your system continuously via Sar and other system commands. It also allows notifications to alarm you once a threshold is reached. SysUsage itself can be run from a centralized place where all the collected statistics are also being stored. It has a web interface where you can view all the stats.

![sysusage](/blog/assets/img/infrastructure_monitoring/sysusage.png)

More info on the [ SysUsage Official site](http://sysusage.darold.net/)

---

### `brainypdm`
**BrainyPDM** _(a.k.a. Brainy Performance Data Management)_ is an open source system performance data management and monitoring tool. It gathers performance data management and monitoring tool that has the capability to gather data from nagios or another generic source to make graphs. It’s cross-platform, has custom graphs and is web based.

![brainypdm](/blog/assets/img/infrastructure_monitoring/brainypdm.png)

BrainyPDM project [summary](https://www.openhub.net/p/brainypdm)

---

### `pcp`
**Performance Co-Pilot** is a system performance and analysis framework.**PCP** has the capability of collating metrics from multiple hosts and does so efficiently. It also has a plugin framework so you can make it collect specific metrics that is important to you. You can access graph data through either a web interface or a GUI. Good for monitoring large systems.

![pcp](/blog/assets/img/infrastructure_monitoring/pcp.png)

---

### [KDE System Guard](https://userbase.kde.org/KSysGuard)
This tool is both a system monitor and task manager. You can view server metrics from several machines through the worksheet and if a process needs to be killed or if you need to start a process it can be done within KDE system guard.

![kde](/blog/assets/img/infrastructure_monitoring/kde.png)

---

### [Munin](http://munin-monitoring.org/)
`Munin` is both a network and a system monitoring tool which offers alerts for when metrics go beyond a given threshold. It uses RRDtool to create the graphs and it has web interface to display these graphs. Its emphasis is on plug and play capabilities with a number of plugins available.

![munin](/blog/assets/img/infrastructure_monitoring/munin.png)

---

### [Nagios](http://www.nagios.org/)

Nagios is system and network monitoring tool that helps you monitor monitor your many servers. It has support for alerting for when things go wrong. It also has many plugins written for the platform.
**Nagios XI** provides monitoring of all mission-critical infrastructure components including applications, services, operating systems, network protocols, systems metrics, and network infrastructure. Hundreds of third-party addons provide for monitoring of virtually all in-house and external applications, services, and systems.

![nagios](/blog/assets/img/infrastructure_monitoring/nagios.png)

---

### [Zenoss](http://www.zenoss.com/)
**Zenoss** provides a web interface that allows you to monitor all system and network metrics. Moreover it discovers network resources and changes in network configurations. It has alerts for you to take action on and it supports the Nagios plugins.

![zenoss](/blog/assets/img/infrastructure_monitoring/zenoss.png)

---

### [Cacti](http://www.cacti.net/)
(And one for luck!) Cacti is network graphing solution that uses the RRDtool data storage. It allows a user to poll services at predetermined intervals and graph the result. Cacti can be extended to monitor a source of your choice through shell scripts.

![cacti](/blog/assets/img/infrastructure_monitoring/cacti.png)

---

### [Zabbix Monitoring](http://www.zabbix.com/)
**Zabbix** is an open source infrastructure monitoring solution. It can use most databases out there to store the monitoring statistics. The Core is written in C and has a frontend in PHP. If you don’t like installing an agent, Zabbix might be an option for you.

![zabbix](/blog/assets/img/infrastructure_monitoring/zabbix.png)

---

### [nmon](http://nmon.sourceforge.net/pmwiki.php)

**nmon** either outputs the data on screen or saves it in a comma separated file. You can display CPU, memory, network, filesystems, top processes. The data can also be added to a RRD database for further analysis.

![nmon](/blog/assets/img/infrastructure_monitoring/nmon.png)

---

### [conky](http://conky.sourceforge.net/)

**Conky** monitors a plethora of different OS stats. It has support for IMAP and POP3 and even support for many popular music players! For the handy person you could extend it with your own scripts or programs using Lua.

![conky](/blog/assets/img/infrastructure_monitoring/conky.png)

---
