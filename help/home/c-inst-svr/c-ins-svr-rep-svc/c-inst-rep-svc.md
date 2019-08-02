---
description: The Insight ServerReplication Service enables you to transmit the event data collected and stored on one Insight Server machine to another Insight Server machine.
seo-description: The Insight ServerReplication Service enables you to transmit the event data collected and stored on one Insight Server machine to another Insight Server machine.
seo-title: Installing the Replication Service
solution: Insight
title: Installing the Replication Service
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
index: y
internal: n
snippet: y
---

# Installing the Replication Service{#installing-the-replication-service}

The Insight ServerReplication Service enables you to transmit the event data collected and stored on one Insight Server machine to another Insight Server machine.

 Typically, the machine on which the data is collected and stored is configured to run as a [!DNL Repeater] machine. See [Repeater Functionality](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md#concept-78613328ece345b2937cd6e43d7f31f2). The [!DNL Replication Service], which is configured by the [!DNL Replicate.cfg] file, enables an [!DNL Insight Server] machine to retrieve data from the [!DNL Repeater] machine and store it locally. The [!DNL Insight Server] machine is referred to as the target machine. Multiple [!DNL Insight Server] DPUs can connect to a single [!DNL Repeater] to request copies of the event data for inclusion in multiple datasets.

You can use the [!DNL Replication Service] in network infrastructures with multiple layers of firewalling to achieve single-port to single-port communications between components that are separated by firewalls.

**To install the [!DNL Replication Service]**

The [!DNL Replicate.cfg] file should be installed as part of your [!DNL Insight Server] installation. You can find the file within the [!DNL Components] folder of your [!DNL Insight Server] installation directory. If you do not have this file, contact Adobe. 
