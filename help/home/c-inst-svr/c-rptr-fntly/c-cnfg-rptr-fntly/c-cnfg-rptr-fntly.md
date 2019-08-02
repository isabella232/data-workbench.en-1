---
description: Repeater functionality enables an Insight Server FSU to receive Sensor-acquired event data from one or more sources and replicate the data to one or more Insight Server FSUs running the Insight ServerReplication Service.
seo-description: Repeater functionality enables an Insight Server FSU to receive Sensor-acquired event data from one or more sources and replicate the data to one or more Insight Server FSUs running the Insight ServerReplication Service.
seo-title: Configuring Repeater Functionality
solution: Insight
title: Configuring Repeater Functionality
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
index: y
internal: n
snippet: y
---

# Configuring Repeater Functionality{#configuring-repeater-functionality}

Repeater functionality enables an Insight Server FSU to receive Sensor-acquired event data from one or more sources and replicate the data to one or more Insight Server FSUs running the Insight ServerReplication Service.

See [Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). This feature enables data replication to redundant facilities for disaster recovery purposes. The target servers act as network clients, connecting to the source FSU to request copies of the event data for inclusion in multiple datasets.

You can use repeater functionality in network infrastructures with multiple layers of firewalling to achieve single-port to single-port communications between components that are separated by firewalls.

For information about the system requirements for installing, configuring, and operating [!DNL Repeater], see the *Minimum System Requirements* document.

To install [!DNL Repeater], you must perform the steps listed for the following two procedures:

* [Configuring an Insight Server FSU for Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configuring Access Control for Target Machines](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

If network firewalls allow access to your [!DNL Repeater] from [!DNL Insight], you can create a connection as described in [Creating a Connection Between Insight and Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118). 
