---
description: Upgrading server components for Data Workbench 6.1 from 5.4 installation.
solution: Analytics
title: DWB Server upgrade  5.4 to 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
---

# DWB Server upgrade: 5.4 to 5.5{#dwb-server-upgrade-to}

Upgrading server components for Data Workbench 6.1 from 5.4 installation.

 Consequently, upgrading from [!DNL Insight] 5.4 to [!DNL Insight] 5.5 is relatively simple.

You can also upgrade directly from [!DNL Insight] 5.3 to [!DNL Insight] 5.5 using the steps below. Make sure you perform all upgrade tasks listed in the [Upgrading from Insight 5.4 to 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) section and the [Upgrading from Insight 5.4 to 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) section. 

1. Stop the [!DNL Insight Server] services on all servers in the cluster except for the [!DNL Insight Master Server].

    1. Copy the new [!DNL ReportServer.exe] and [!DNL Insight.exe] files to the Software\Insight folder. 
    
    1. After the [!DNL Insight] client has updated, copy the [!DNL InsightServer.exe] and [!DNL InsightServer64.exe] files into the \Bin folder. 
    
    1. Wait for the [!DNL Insight Master Server] to start, then verify the version running via the [!DNL Connections] visualization.

1. On the cluster’s [!DNL Master Server] in the [!DNL Insight] client:

    1. Make a local copy of the existing [!DNL Base] profile and rename it (for example, BaseBackup). 
    1. Copy the new [!DNL Base] profile to the Profiles folder. 
    1. Repeat these two steps for the Transform folder.

1. Copy the Scripts folder from the server package onto the [!DNL Master Server] into the Server installation directory.
1. Copy the [!DNL Terrain Images.cfg.off] file into the Components folder of the [!DNL Master Server].
**To upgrade client software from [!DNL Insight] 5.4 to 5.5**

In the [!DNL Insight.cfg] file, make sure that the Update Software setting is set to TRUE. 
