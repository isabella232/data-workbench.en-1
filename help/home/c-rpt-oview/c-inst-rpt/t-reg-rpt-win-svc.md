---
description: Steps to register and run Report Server.
seo-description: Steps to register and run Report Server.
seo-title: Registering Report Server as a Windows Service
solution: Analytics
title: Registering Report Server as a Windows Service
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
index: y
internal: n
snippet: y
---

# Registering Report Server as a Windows Service{#registering-report-server-as-a-windows-service}

Steps to register and run Report Server.

Before you perform this procedure, identify the Windows account under which the [!DNL Report Server] service will run. Make sure that this account has the proper permissions to access the location where generated reports are stored (that is, do not use the [!DNL Local System Account]).

Use the procedure below to start [!DNL Report Server]. When you start [!DNL Report Server] for the first time, it automatically registers itself as a Windows service.

When you start [!DNL Report Server] for the first time, it automatically connects to the Adobe License Server to register your digital certificate. To complete the registration process successfully, your machine must be connected to the Internet when you execute the following steps. 

1. In Windows, navigate to the directory where you installed [!DNL Report Server].

   Example: D:\Adobe\Report 

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. To confirm that [!DNL Report Server] is running correctly, click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. This command sequence can vary depending on which version of Windows you are using.
1. In the service list, locate the entry for [!DNL Report Server] and confirm that its status is Started and its startup type is Automatic.
1. Do the following to specify the user account under which [!DNL Report Server] will execute:

    1. Double-click **[!UICONTROL Report Server]** to open the [!DNL Properties] window. 
    
    1. Select the **[!UICONTROL Log On]** tab. 
    1. Select the **[!UICONTROL This account]** radio button. 
    1. Type or browse for the account name. This account must have permission to access the location where generated reports are stored.

       >[!NOTE]
       >
       >If [!DNL Report Server] distributes reports as Microsoft Excel ( [!DNL .xls] or [!DNL .xlsx]) files, make sure that the account also has permission to run Microsoft Excel.

    1. Enter and confirm the password for the account. 
    1. Click **[!UICONTROL OK]**.

1. Right-click the [!DNL Report Server] service and select **[!UICONTROL Restart]** to restart the service under the account you specified.
1. To check whether [!DNL Report Server] experienced any errors during start-up, click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. This command sequence can vary depending on which version of Windows you are using.

    1. In the left pane of the [!DNL Event Viewer] window, select the Applications log. 
    1. In the right pane, look for events with Adobe in the [!DNL Source] column. 
    1. If you find an error from Adobe, double-click the error to display the [!DNL Event Properties] window. This window provides detailed information about the error.

       >[!NOTE]
       >
       >After the [!DNL Report Server] service starts, the file [!DNL ReportServer.log] is created in the Report Server [!DNL Trace] directory. This file is also useful for troubleshooting issues with [!DNL Report Server].

You have completed the installation of [!DNL Report Server]. [!DNL Report Server] is designed to run continuously. If you restart the machine, [!DNL Report Server] restarts automatically. If you need to start and stop [!DNL Report Server] manually, you can do so using the [!DNL Services] control panel in Windows. 
