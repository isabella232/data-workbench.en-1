---
description: Before you can generate reports and alerts, you must configure Report Server to specify the address of the Insight server and identify the profiles that you want it to report against.
seo-description: Before you can generate reports and alerts, you must configure Report Server to specify the address of the Insight server and identify the profiles that you want it to report against.
seo-title: Configuring the Connection to the Insight Server
solution: Analytics
title: Configuring the Connection to the Insight Server
topic: Data workbench
uuid: 3b45f98b-6b16-493b-bfa1-888993cd57a3
index: y
internal: n
snippet: y
---

# Configuring the Connection to the Insight Server{#configuring-the-connection-to-the-insight-server}

Before you can generate reports and alerts, you must configure Report Server to specify the address of the Insight server and identify the profiles that you want it to report against.

>[!NOTE]
>
>Until you configure Report Server as described below, you can not run Report Server successfully. If you attempt to run Report Server with the non-configured file that is installed with the program, Report Server produces a stream of errors.

**To configure Report Server** 

1. With Windows Explorer, navigate to the directory where you installed Report Server.
1. Open the [!DNL ReportServer.cfg] file in Notepad and modify the file as desired.

   The following sample [!DNL Report Server.cfg] contains only the parameters included in the [!DNL Report Server.cfg] file by default (and highlights the required parameter settings). If you contact the Adobe License Server through a proxy server, you need to add the Licensing vector and its parameters. See [Report Server.cfg parameters](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) for a detailed description.

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Save and close the file.
