---
description: The Detailed Status interface in data workbench is useful for troubleshooting errors or other issues with the Data Workbench Server and Report Server machines that are clients of Data Workbench Server.
seo-description: The Detailed Status interface in data workbench is useful for troubleshooting errors or other issues with the Data Workbench Server and Report Server machines that are clients of Data Workbench Server.
seo-title: Displaying Report Server Status
solution: Analytics
title: Displaying Report Server Status
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
index: y
internal: n
snippet: y
---

# Displaying Report Server Status{#displaying-report-server-status}

The Detailed Status interface in data workbench is useful for troubleshooting errors or other issues with the Data Workbench Server and Report Server machines that are clients of Data Workbench Server.

To view Report’s status in the [!DNL Master Server Detailed Status] interface, you must add a report status server to the [!DNL Servers] vector in data workbench server’s [!DNL Communications.cfg] file. The following procedure describes how to add the report status server to the [!DNL Communications.cfg] file:

For more information about [!DNL Detailed Status] interfaces, see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

**To add a [!DNL Report Status Server]** 

1. Navigate to the Components folder in the directory where you installed the data workbench server (InsightServer64.exe.)

   Example: [!DNL C:\Adobe\Server\Components]
1. Open [!DNL Communications.cfg] in a text editor such as Notepad.
1. Locate the [!DNL Servers] vector and add the report status server to this vector as highlighted in the following file fragment.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Update the items count for the [!DNL Servers] vector (that is, increment the items value by one) as highlighted in the file fragment in the previous step.
1. Save the file.
