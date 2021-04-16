---
description: Procedure to start Insight Server and simultaneously register it as a Microsoft Windows Service.
title: Registering Insight Server as a Windows Service
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
---
# Registering Insight Server as a Windows Service{#registering-insight-server-as-a-windows-service}

Procedure to start Insight Server and simultaneously register it as a Microsoft Windows Service.

>[!NOTE]
>
>When you start [!DNL Insight Server] for the first time, it automatically connects to the Adobe License Server to register your digital certificate. To complete the registration process successfully, your machine must be connected to the Internet when you execute the following steps.

**To start [!DNL Insight Server] and register it as a Windows Service**

1. Open a command prompt and navigate to the bin sub-directory in the folder where you installed [!DNL Insight Server].

   Example: [!DNL C:\Adobe\Server\bin] 

1. At the command prompt, execute the following command to start [!DNL Insight Server] and simultaneously register it to run as a service under Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. To confirm that [!DNL Insight Server] is running correctly, click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. This command sequence can vary depending on which version of Windows you are using.

   1. In the service list, locate the entry for **[!DNL Adobe Insight Server]** and confirm that its status is Started and its startup type is Automatic. 
   1. Close the Services control panel.

1. To check whether [!DNL Insight Server] experienced any errors during start-up, click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. This command sequence can vary depending on which version of Windows you are using.

   1. In the left pane of the [!DNL Event Viewer] window, select the **[!UICONTROL Application]** log.
   1. In the right pane, look for events with “Adobe” in the [!DNL Source] column.
   1. If you find an error from “Adobe,” double-click the error to display the [!DNL Event Properties] window. This window provides detailed information about the error.

1. When you finish examining the [!DNL Applications] log, close the Event Viewer.

You have completed the installation of [!DNL Insight Server]. [!DNL Insight Server] is designed to run continuously. If you restart the machine, [!DNL Insight Server] restarts automatically. If you need to start and stop [!DNL Insight Server] manually, you can do so using the Services control panel in Windows. As described in the following section, you can optionally configure [!DNL Insight Server] service to automatically restart periodically.

## Configuring the Service to Restart Automatically {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] is designed to continue running uninterrupted. It is typically stopped or started only when performing infrequent tasks such as software upgrades or certificate changes or in the event of certain system errors. It is not necessary to stop or restart the [!DNL Insight Server] service during normal system operation; however, you can configure the service to restart periodically (daily, weekly, or monthly) to, for example, clear the event messages.

**To configure the [!DNL Insight Server] service to restart automatically**

1. Navigate to the [!DNL Components] folder in the directory where you installed [!DNL Insight Server].

   Example: [!DNL C:\Adobe\Server\Components] 

1. Use a text editor such as Notepad to create a new file called [!DNL ScheduledRestart.cfg]. 
1. Enter the following text in the [!DNL ScheduledRestart.cfg] file: 

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> For this value... </th> 
      <th colname="col2" class="entry"> Specify </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Month DD, YYYY HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>The time when you want <span class="keyword"> Insight Server </span> to be restarted for the first time. </p> <p>Example: August 13, 2013 22:30:00 EST </p> <p> <p>Note:  You must specify a time zone. The time zone does not default to system time if not specified. If you wish to implement Daylight Saving Time or a similar clock-shifting policy, you must save the <span class="filepath"> .dst </span> file containing the appropriate rules in the Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> machine. For a list of supported time zone abbreviations and information about implementing Daylight Saving Time, see <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Time Zone Codes </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequency</i> </td> 
      <td colname="col2"> <p>One of the following values: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">week </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>To indicate the frequency at which you want <span class="keyword"> Insight Server </span> to be restarted after the initial time specified in Start Time. </p> <p>For example, if you wanted <span class="keyword"> Insight Server </span> to restart once a week, you would set this value to “week.” </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   Verify that the [!DNL ScheduledRestart.cfg] file is in the [!DNL Components] folder in the directory where you installed [!DNL Insight Server].
