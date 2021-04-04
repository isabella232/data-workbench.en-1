---
description: Follow these steps to update to data workbench v6.1 from your Insight v5.5x installation.
solution: Analytics
title: Data Workbench 5.5 to 6.1 Upgrade
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86
exl-id: 3f25917b-b929-4e3b-84f0-1a81b30ba641
---
# Data Workbench 5.5 to 6.1 Upgrade{#data-workbench-to-upgrade}

Follow these steps to update to data workbench v6.1 from your Insight v5.5x installation.

**Step 1**: [Server Upgrade](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Step 2**: [Report Server Upgrade](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Step 3**: [Client Upgrade](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>The server, report server, and client components are upgraded to run on 64-bit Windows operating systems.

## Server Upgrade {#section-08bd6fe3da8740fcb19688e8cac6f223}

Follow these steps to update the **[!UICONTROL Server v6.1]** components:

1. Using the **[!UICONTROL Software and Docs]** profile, open the **[!UICONTROL Start Here]** workspace and download all needed server packages to a local folder.

    * Download **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip folders and extract all files.

      The **[!UICONTROL Server]** package includes **[!UICONTROL Lookup]** and **[!UICONTROL Profile]** folders with the **[!UICONTROL Base]** and **[!UICONTROL Transform]** lookup files to add and replace to update the server. 
    
    * Download new **[!UICONTROL Profiles]** folders. 
    * Download updated **[!UICONTROL Lookup]** folders. 
    * Download the **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** package. 
    * Download additional **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]**, and **[!UICONTROL Dashboard]** files as needed for your system.

1. Stop the **[!UICONTROL Adobe Insight Server]** service.

   ![](assets/install_server_download1.png)

1. From the downloaded **[!UICONTROL Server]** package:

    1. Replace the [!DNL Server\Bin] folder to update the [!DNL InsightServer64.exe] and supporting files. 
    
    1. Replace the [!DNL Server\Profiles] folder. You can overwrite all files. 
    1. Update the [!DNL Server\Lookups] folder. You will want to add the newly downloaded files to the custom files already located in the folder. 
    1. Replace the [!DNL Server\Software] folder to update [!DNL Insight.exe] and [!DNL ReportServer.exe] 
    
    1. Update the [!DNL Server\Scripts] folder to update [!DNL TnTSend.exe].

1. If you employ **[!UICONTROL DeviceAtlas]**, then you will need to [update the bundle](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) located in the [!DNL Server\Lookups] folder. 
1. Set [!DNL Directories] in the [!DNL Profile.cfg] file to ensure that the vector is updated to reflect the number of items for each profile.

   For example, to enable the **[!UICONTROL Predictive Analytics]** profile you will need to update this setting.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure and save the [!DNL PAServer.cfg] file to upgrade the Predictive Analytics feature.

   If you want to submit Predictive Analytics jobs to the servers, then you will need to configure the [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] file to manage server-side clustering submissions.

   The custom profile should inherit the settings from the Predictive Analytics configuration profile, allowing you to configure and save the [!DNL PAServer.cfg] based on your site's implementation. 

1. Define the **[!UICONTROL Log Source ID]**.

   The **[!UICONTROL Recording of Rows per Log Source]** was added in **[!UICONTROL v6.04]** and defined in the custom profile’s [!DNL Log Processing.cfg] file by adding a uniquely named **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   If you do not have the Log Source ID defined, then you will get the following error:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Because the [!DNL EventMessages.dll] has been updated, it is required that you unregister and then register the **[!UICONTROL Adobe Insight Server]** across the cluster.

    * [!DNL InsightServer64.exe /unregserver]
    * [!DNL InsightServer64.exe /regserver]

1. Start the **[!UICONTROL Adobe Insight Server]** service across the cluster.

The server installation is now complete.

## Report Server Upgrade {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Before upgrading to **[!UICONTROL Report Server v6.1]**, you must first upgrade to **[!UICONTROL Server v6.1]**.

1. Using the **[!UICONTROL Software and Docs]** profile, download **[!UICONTROL v6.1]** from the **[!UICONTROL Report Server]** package to a local folder. 
1. Copy **[!UICONTROL Report Server 6.1]** from the downloaded package and replace the profile packages.

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the [!DNL install] folder is a backup file used for localization, and must be present in the [!DNL install] directory. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.

1. (optional) Modify the report server configuration file to support double-byte characters.

   Data workbench currently supports English (-en-us) and Chinese (-zh-cn). You need to set a font to support single and double-byte characters:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   The Windows operating system must also have the listed fonts installed. 

1. Configure [!DNL Report Server v6.1].

    1. Stop the **[!UICONTROL Adobe Insight Report Server]** service. 
    1. Launch a command prompt as an "Administrator". 
    1. Navigate to the Report Server [!DNL install] folder. 
    1. Delete the Report Server service using the following command:     
    
       ```    
       ReportServer.exe /unregserver
       ```

1. Start the service based on the language settings: 

   ```
   ReportServer.exe -RegServer -Locale -en-us (English) 
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. To verify that Report Server is running with the correct settings, open up **[!UICONTROL Windows Service Manager]** and right-click **[!UICONTROL Adobe Insight Report Server - Properties]**. The path to the executable will display the updated command-line settings.

The report server installation is now complete.

## Client Upgrade {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Before upgrading to **[!UICONTROL Client v6.1]**, the administrator must first upgrade to **[!UICONTROL Server v6.1.]**

1. Launch [!DNL Insight.exe] but DO NOT connect to any profiles. 
1. Edit the [!DNL Insight.cfg] file to not update software automatically.

   ```
   Update Software = bool: false
   ```

1. Connect to **[!UICONTROL Software and Docs]** profile (softdocs). 
1. Download [!DNL Software\Insight Client\v6.10]. 
1. (optional) Modify [!DNL insight.cfg] to support double-byte characters.

   Data workbench currently supports both English and Simplified Chinese. Select fonts to support both of these languages:

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Exit out of the client. 
1. Copy the files in the downloaded **v6.1** client package to the [!DNL Install] folder. 

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the install folder is a backup file used for localization, and must be present in the install directory. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up. 
   >
   >For example, to launch Simplified Chinese, create a shortcut that passes in the command-line setting. 
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >If you want to launch in English (default), then no command-line change is necessary.

1. Launch [!DNL Insight.exe] for English or the shortcut that you created for another language. 
1. Connect to your profile and allow the client to synchronize with the server. 
1. (optional) To employ the IME, make these changes to the [!DNL Insight.cfg] file: 

   ```
   Localized IME = bool: true
   ```

   The Input Method Editor (IME) allows you to input international characters. 

1. (optional) Edit the [!DNL Insight.cfg] file to automatically update software: 

   ```
   Update Software = bool: true
   ```

   See instructions for implementing the IME. 
1. Restart again after the profile synchronization to employ the most recent [!DNL .zbin] file.

The client installation is now complete.
