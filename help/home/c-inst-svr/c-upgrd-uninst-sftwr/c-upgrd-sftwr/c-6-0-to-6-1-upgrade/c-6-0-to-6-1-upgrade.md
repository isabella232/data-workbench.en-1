---
description: Follow these steps to update to data workbench v6.1 from your data workbench v6.0x installation.
seo-description: Follow these steps to update to data workbench v6.1 from your data workbench v6.0x installation.
seo-title: Data Workbench 6.0 to 6.1 Upgrade
solution: Analytics
title: Data Workbench 6.0 to 6.1 Upgrade
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
---

# Data Workbench 6.0 to 6.1 Upgrade{#data-workbench-to-upgrade}

Follow these steps to update to data workbench v6.1 from your data workbench v6.0x installation.

 **Step 1**: [Server upgrade](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Step 2**: [Report Server upgrade](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Step 3**: [Client upgrade](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>The server, report server, and client components are upgraded to run on 64-bit Windows operating systems.

## Server Upgrade {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Follow these steps to update the **[!UICONTROL Server v6.1]** components:

1. Using the **[!UICONTROL Software and Docs]** profile, open the **[!UICONTROL Start Here]** workspace and download all needed server packages to a local folder.

    * Download **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip folders and extract all files.

      The Server package includes **[!UICONTROL Lookup]** and **[!UICONTROL Profile]** folders with **[!UICONTROL Base]** and **[!UICONTROL Transform]** profiles to update the server. 
    
    * Download the **[!UICONTROL Profiles]** folders. 
    * Download the **[!UICONTROL Lookup]** folders. 
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

1. If you employ **[!UICONTROL DeviceAtlas]**, then you will need to [update the bundle](https://marketing.adobe.com/resources/help/en_US/insight/dataset/c_deviceAtlas_update.html) located in the [!DNL Server\Lookups] folder. 

1. Configure the [!DNL Profile.cfg] file to ensure that the vector is updated to reflect the number of items for each profile.

   For example, to enable the **[!UICONTROL Predictive Analytics]** profile you will need to update this setting.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure and save the PAServer.cfg file for the Predictive Analytics feature.

   If you want to submit Predictive Analytics jobs to the servers, then you will need to configure the [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] file to manage server-side clustering submissions.

   The custom profile should inherit the settings from the Predictive Analytics configuration profile, allowing you to configure and save the [!DNL PAServer.cfg] file based on your site's implementation. 

1. Define the **[!UICONTROL Log Source ID]**.

   The **[!UICONTROL Recording of Rows per Log Source]** was added in **[!UICONTROL v6.04]** and defined in the custom profile’s [!DNL Log Processing.cfg] file by adding a uniquely named **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg 
        
<b>Log Source ID = string: <<i>Name your ID Here</i>></b>
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

1. (optional) Data workbench currently supports English (-en-us) and Chinese (-zh-cn). You need to set a font to support single and double-byte characters: 

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   The Windows operating system must also have the listed fonts installed. 

1. Configure [!DNL Report Server v6.1] for localization.

    1. Stop the **[!UICONTROL Adobe Insight Report Server]** service. 
    1. Launch a command prompt as an "Administrator". 
    1. Navigate to the Report Server [!DNL install] folder. 
    1. Delete the Report Server service using the following command:     
    
       ```    
       ReportServer.exe /unregserver
       ```    
    
    1. Start the service based on language settings:     
    
       ```    
       ReportServer.exe -RegServer -Locale -en-us (English)  
       ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
       ```

1. To verify that Report Server is running with the correct settings, open up **[!UICONTROL Windows Service Manager]** and right-click **[!UICONTROL Adobe Insight Report Server - Properties]**. The path to the executable will display the updated command-line settings.

The report server installation is now complete.

## Client Upgrade {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Before upgrading to **[!UICONTROL Client v6.1]**, the administrator must first upgrade to **[!UICONTROL Insight Server v6.1.]**

1. Launch [!DNL Insight.exe] but do not connect to any profiles. 
1. Edit the [!DNL Insight.cfg] file.

   ```
   Update Software = bool: true
   ```

1. Connect to your profile.

   Allow the client to synchronize with the server and your client will be upgraded with the latest v6.1client profiles, executables, and configuration files.

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the [!DNL install] folder is a backup file used for localization and must be present. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.

   See [setting up localized languages](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) to add an [!DNL insight.zbin] file required for localized settings.

**Additional Client Settings**

Before configuring [!DNL Insight.exe] and supporting files, you must exit the client application.

To install Simplified Chinese:

1. Create a shortcut that passes in the command-line setting to the [!DNL Insight.exe] file. 

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] to support single and double-byte font characters.

   Data workbench currently supports both English and Simplified Chinese. You can select fonts to support both of these languages:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   The Windows operating system must also have the requested fonts installed. 

1. Launch the shortcut that you created to synchronize profiles and the updated . [!DNL zbin] file.

To employ the Input Method Editor (IME).

IME allows you to input international characters.

1. Update the [!DNL Insight.cfg] file with these settings:

   ```
   Localized IME = bool: true
   ```

1. Launch the shortcut that you created to synchronize profiles and the updated [!DNL .zbin] file.

The client installation is now complete. 
