---
description: The Report Portal uses the information in a configuration file called global.asa to initialize user sessions.
solution: Analytics
title: Edit the Session Configuration File
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
---

# Edit the Session Configuration File{#edit-the-session-configuration-file}

The Report Portal uses the information in a configuration file called global.asa to initialize user sessions.

 When you install [!DNL Report Portal], you must edit this file as indicated. The [!DNL global.asa] file resides in the \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Do not change any other parameters in this configuration file.

1. On the machine where IIS is running, open the [!DNL global.asa] file in a text editor such as Notepad.
1. Optional. To let users access [!DNL Report Portal] without authentication, change the Session(“In”) parameter value to true. The default is false, which authenticates all users who attempt to access [!DNL Report Portal].
1. If your [!DNL Report Portal] is installed on a drive other than the C drive, change the value of the Session(“Drive”) parameter to the correct drive location.
1. For the Session(“DBPath”) parameter, change the value to reflect the path to the database that contains the information needed to authenticate [!DNL Report Portal] users. Do not include the drive letter, but make sure to include a trailing slash.

   Example: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Save the file.
1. To verify that the [!DNL Report Portal] files have been installed correctly and can be reached through their designated virtual directory, open the following page in your browser:

   http://*YourServerAddress*/*YourPortalName*

   Example: [!DNL http://localhost/VisualReportPortal]

   If the [!DNL Report Portal] ASPs have been installed correctly, you should see the portal login page. If you do not see this page, verify that ASPs are enabled on your IIS and double-check your virtual directory mappings. 

