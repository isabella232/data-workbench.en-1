---
description: The instructions for installing an Insight Server FSU and configuring it for administrative use are very similar to those for installing and configuring an Insight Server DPU.
solution: Analytics
title: Installation Procedures for an Insight Server FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
---
# Installation Procedures for an Insight Server FSU{#installation-procedures-for-an-insight-server-fsu}

The instructions for installing an Insight Server FSU and configuring it for administrative use are very similar to those for installing and configuring an Insight Server DPU.

For *MS System Center Endpoint Protection* in Windows 2012 Servers, these executables need to be added to the **Excluded Processes:**

* [!DNL InsightServer64.exe] 
* [!DNL ReportServer.exe] 
* [!DNL ExportIntegration.exe]

To install and configure an [!DNL Insight Server] FSU, you must complete the following tasks: 

1. Install the [!DNL Insight Server] program files.
1. Install the [!DNL Insight Server] digital certificate.
1. Check the port settings in the [!DNL Communications.cfg] file.
1. Modify the [!DNL Access Control.cfg] file to allow administrative access to [!DNL the Server] from [!DNL the Client].
1. Modify the [!DNL server.address] file to define the server’s network location.
1. Set Windows memory utilization parameters as described.
1. Register [!DNL Insight Server] as a Windows service as described.

   For instructions to configure data sources, permissions, and communications for an [!DNL Insight Server] FSU, see the *Dataset Configuration Guide*.
