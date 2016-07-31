---
layout: post
title: Infrastructure Monitoring Tools
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

![opennms](/assets/img/infrastructure_monitoring/opennms.png)

More info on the [opennms official site](http://www.opennms.org/en)

---

### `SysUsage`
`SysUsage` monitors your system continuously via Sar and other system commands. It also allows notifications to alarm you once a threshold is reached. SysUsage itself can be run from a centralized place where all the collected statistics are also being stored. It has a web interface where you can view all the stats.

![sysusage](/assets/img/infrastructure_monitoring/sysusage.png)

More info on the [ SysUsage Official site](http://sysusage.darold.net/)

---

### `brainypdm`
**BrainyPDM** _(a.k.a. Brainy Performance Data Management)_ is an open source system performance data management and monitoring tool. It gathers performance data management and monitoring tool that has the capability to gather data from nagios or another generic source to make graphs. It’s cross-platform, has custom graphs and is web based.

![brainypdm](/assets/img/infrastructure_monitoring/brainypdm.png)

BrainyPDM project [summary](https://www.openhub.net/p/brainypdm)

---


