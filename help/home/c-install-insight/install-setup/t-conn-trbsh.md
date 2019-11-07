---
description: If Insight cannot connect to the Insight Server(s) using the specified settings, a red node appears in the Servers Manager.
title: Connection Troubleshooting
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
---

# Connection Troubleshooting{#connection-troubleshooting}

If Insight cannot connect to the Insight Server(s) using the specified settings, a red node appears in the Servers Manager.

This might occur, for example, if you configure the connection incorrectly or you do not have permission to view the [!DNL Insight Server’s] status.

**To determine why Insight is not able to establish a connection** 

1. Right-click the red server node and click **[!UICONTROL Detailed Status]**.
1. In the [!DNL Detailed Status] interface, click **[!UICONTROL Network Connections]** and expand the numbered items. The [!DNL Status] parameter provides information about why Insight is not able to establish a connection:

    * A status code in the 500s indicates a configuration error. 
    * A status code of 403 usually indicates that you do not have permission to view the server’s status.

You can view additional status information in the [!DNL insight.log] file. This log file is located in the [!DNL Trace] folder in the directory where you installed Insight. To view the file, open it in a text editor such as Notepad.

If you need assistance understanding the information in the [!DNL insight.log] file, first contact your system administrator. If you require further assistance, contact Adobe Customer Care. 
