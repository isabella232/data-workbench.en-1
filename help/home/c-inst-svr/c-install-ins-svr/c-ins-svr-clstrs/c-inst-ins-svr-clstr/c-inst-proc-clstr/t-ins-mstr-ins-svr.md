---
description: To use a cluster, you must designate one Insight Server in the cluster to act as the master Insight Server.
solution: Analytics
title: Installing the Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
---
# Installing the Master Insight Server{#installing-the-master-insight-server}

To use a cluster, you must designate one Insight Server in the cluster to act as the master Insight Server.

 A client component such as [!DNL Insight] or [!DNL Report] connects to the master [!DNL Insight Server] at the beginning of a session. At subsequent points during the session, the client might connect to other [!DNL Insight Servers] in the cluster to perform a query. These subsequent connections between the client and the other [!DNL Insight Servers] in the cluster are brokered by the master [!DNL Insight Server] and are transparent to the client.

Besides brokering connections between a client and other [!DNL Insight Servers] in the cluster, the master [!DNL Insight Server] acts as the central administrative point for the entire cluster. When you administer a cluster, you update the master [!DNL Insight Server]. The administrative changes that you make on the master [!DNL Insight Server] are retrieved by the other [!DNL Insight Servers] in the cluster.

**To install the master [!DNL Insight Server]** 

1. Determine which machine will act as the master [!DNL Insight Server].
1. Install and configure [!DNL Insight Server] (typically, an [!DNL Insight Server] FSU) on this machine as described in [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Install [!DNL Insight] and configure a connection to the master [!DNL Insight Server] as described in the *[!DNL Insight] User Guide*.
