---
description: An Insight Server cluster is required when the amount of data you want to process and make accessible to your users of Insight and Report exceeds the capacity of a single Insight Server.
solution: Insight
title: About Insight Server Clusters
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
---

# About Insight Server Clusters{#about-insight-server-clusters}

An Insight Server cluster is required when the amount of data you want to process and make accessible to your users of Insight and Report exceeds the capacity of a single Insight Server.

 By setting up an [!DNL Insight Server] cluster, you can distribute a single analysis dataset across multiple machines in a cluster to harness the processing power of multiple [!DNL Insight Servers].

The first step in the implementation of an [!DNL Insight Server] cluster is to allocate the [!DNL Insight Server] machines in your cluster. The first [!DNL Insight Server] machine that you set up is your master [!DNL Insight Server] (sometimes referred to as your primary [!DNL Insight Server]).

>[!NOTE]
>
>If you are using an [!DNL Insight Server] File Server Unit (FSU), Adobe recommends that you configure the FSU as your master [!DNL Insight Server]. For information about configuring an FSU, see the *Dataset Configuration Guide*.

The master [!DNL Insight Server] manages the communication between the other [!DNL Insight Servers] in the cluster (called processing servers or, sometimes, query servers) and instances of [!DNL Insight] and [!DNL Report]. For a given dataset, log file processing occurs on the (one or more) designated [!DNL Insight Servers] (master or processing) as specified in the [!DNL Insight Server] configuration files. When working in a clustered environment, [!DNL Insight] installations are configured to access the master [!DNL Insight Server], but queries can be handled by any of the [!DNL Insight Servers] within the cluster.

>[!NOTE]
>
>The **PAServer.cfg** file. If you want to submit Predictive Analytics clustering jobs to Insight Servers, then you will need to configure the [!DNL PAServer.cfg] file for handling server-side clustering submissions. The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.
>
>```
>PAServer = PAServerConfig: 
>  Master Server = serverInfo: 
>    Address = string: 
>    Port = int: 80
>    Use SSL = bool: false
>```

>[!IMPORTANT]
>
>The instructions in this chapter do not apply to the creation of an [!DNL Insight Server] cluster consisting of more than five (5) [!DNL Insight Servers]. Please contact Adobe to obtain system requirements and profile configuration recommendations for clusters larger than five [!DNL Insight Servers].
