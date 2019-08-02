---
description: New features introduced in Data Workbench 6.0.4, including bug fixes and known issues.
seo-description: New features introduced in Data Workbench 6.0.4, including bug fixes and known issues.
seo-title: Data Workbench 6.0 Release Notes
solution: Analytics
title: Data Workbench 6.0 Release Notes
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
index: y
internal: n
snippet: y
---

# Data Workbench 6.0 Release Notes{#data-workbench-release-notes}

New features introduced in Data Workbench 6.0.4, including bug fixes and known issues.

## New Features {#section-1225066ea8f44cf68e42e019d0bca816}

Data workbench (Insight 6.0) includes these new features and visualizations for added reporting capabilities and predictive analysis tools.

To view previous features and fixes based for each past release, see the [release note archives](https://marketing.adobe.com/resources/help/en_US/insight/insight_release_notes_prev.pdf). 

|  Data Workbench Features  | Description  |
|---|---|
|  [Funnel Visualization](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da)  | The Funnel visualization lets you define the sequential process flow of your customers and provides visibility into the fallout of visitors at each step in the process.  |
|  [Visitor Clustering](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d)  | Clustering lets you leverage customer characteristics to dynamically categorize visitors and generate cluster sets based on selected data inputs for customer analysis and targeting.  |
|  [Correlation Analysis](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c)  | Correlation Analysis lets you quickly identify relevant data relationships to extend and enhance your analysis.  |
|  [Updated DeviceAtlas Distribution](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0)  | The DeviceAtlas JSON file will now be distributed in a .bundle file (a renamed .tar.gz) along with DeviceAtlas.dll and DeviceAtlas64.dll.  |

## Client Upgrade Requirements {#section-f316103b48374b6eac77e8feb5c47ecf}

Complete these upgrade tasks for data workbench (Insight 6.0) client features:

**Updating the .zbin file for the client**

Data workbench now supports an Input Method Editor (IME) as a secondary text entry process that allows you to enter international characters from your keyboard using a floating text box. Data workbench will support English by default but also allows you to load other files to support international languages, such as a virtual Chinese keyboard (Pinyin IME).

A new dictionary file (a .zbin file) is required by the client application before updating to version 6.0. You can obtain the needed .zbin file from the Software and Docs profile (Softdocs).

Prerequisites:

* Before upgrading to the Insight 6.0 client and Report Server 6.0, the Insight administrator must first upgrade to Insight Server 6.0. 
* The Insight administrator will need to choose a zbin file based on language (en-us.zbin, zh-cn.zbin), copy the language file, then rename it to insight.zbin, and place the renamed file in the root directory of the Report Server where the executable is located. Then restart the Insight Report Server.

See the [Server Upgrade Requirements](../../../home/c-release-notes-insight/c-release-notes-insight.md#section-d6edba8b36234957ba8d06b555667a5a) for additional server-side upgrade information.

**To upgrade the zbin file for the client (from version 5.x to 6.0)**:

1. To make sure the client does not get updated from the Insight Server during this upgrade, set your Insight.cfg argument to false. 

   ```
   Update Software = bool: false
   ```

1. Restart the Insight client. 
1. Navigate to the Software and Docs profile (SoftDocs profile) and download the required **[!UICONTROL Insight.zbin]** file: [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Copy the Insight.zbin file to the same folder as the Insight.exe file. 
1. To make sure the Insight client now gets updated from the Insight Server, change the Insight.cfg file argument to true: 

   ```
   Update Software = bool: true
   ```

1. Restart the client.

   Your client will synchronize with the server and you will see a message stating that your client is downloading. At the conclusion of the download, you will get a message asking if your want to restart your Insight client. 
1. Click **OK** to restart the client.

   The client will start and upgrade to version 6.0. 

1. Restart the client again for the Insight.zbin client synchronization to take effect.

   If you get the following message, then it means the zbin was not placed in the correct folder location alongside the Insight.exe file. 

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   To correct the issue, delete Insight.exe and rename the latest version of Insight.exe.old to Insight.exe, and then start again with Step 1 above.

## Server Upgrade Requirements {#section-d6edba8b36234957ba8d06b555667a5a}

Complete these upgrade tasks for Insight 6.0 server features:

**Update all Insight Server 6.0 packages**. Insight 6.0 includes server packages that need to be updated, including the new Predictive Analytics profile.

* 

  >[!IMPORTANT]
  >
  >It is recommended that users upgrade their server clusters with fresh installations of Insight Server 6.0 when updating.

It is also recommended that client upgrade their server clusters with fresh installation of Insight Server 6.0.

Upgrade Server cluster

**Prepare the language file (.zbin file). **The Insight administrator selects the <language>.zbin file for the required language (for example: en-us.zbin , zh-cn.zbin) located in the [!DNL base/localization/<langauge>.zbin] folder. The administrator then copies the language file and renames it to "insight.zbin".

After preparing the language file (.zbin), both the Insight Client and Report Server need to be updated. The Insight Client is updated during the [client upgrade process](../../../home/c-release-notes-insight/c-release-notes-insight.md#section-f316103b48374b6eac77e8feb5c47ecf), but in most cases the Insight administrator will update the Report Server.

**Update Report Server with a language file (.zbin file)**.

For all languages, Report Server 6.0 requires the "insight.zbin" file copied to the Report Server root folder.

Update the Report Server language files:

1. Add the renamed "insight.zbin" file to the root ReportServer directory. 
1. The Report Server configuration file (reportserver.cfg) requires font settings for double-byte languages. For example, Chinese requires the addition of fonts using SimSun: 

   ```
   <b>Report Server.cfg - Add Fonts</b> 
    
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. A parameter for Report Server 6.0 needs to be passed in the command line for localization, for example: 

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >If a locale is not specified, then the Report Server defaults to the language selected in the insight.zbin file.

   Follow the steps to launch the ReportServer as a service with the Locale parameters:

    1. Launch a Command Prompt as an Administrator. 
    1. Navigate to the ReportServer install folder. 
    1. Type the following command to start the service:

        * For English: [!DNL ReportServer.exe -RegServer -Locale -en-us]
        * For Chinese: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. To verify if the ReportServer is running with the correct parameters:

    1. Open up Windows Service Manager. 
    1. Right-click [!DNL Adobe Insight Report Server - Properties].

   The path to executable will contain the parameters:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Modify Profile Configuration file for Predictive Analytics**. Insight administrator will need to modify the custom profile.cfg file to include the Predictive Analytics profile to be available in Insight.

Example of the profile.cfg entry:

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 

```

**Update the PAServer.cfg file**. If you want to submit Predictive Analytics clustering jobs to Insight Servers, then you will need to configure the PAServer.cfg file for handling server-side clustering submissions.

The custom profile should inherit the PAServer.cfg from the Predictive Analytics profile (Server\Profiles\Predictive Analytics\Dataset). Configure and save the PAServer.cfg per your implementation site. 

>[!NOTE]
>
>Once PAServer.cfg is configured and saved to custom profile, an Insight Server restart is required across the site.

**Upgrade Report Server. **You will need to update the fonts and the start-up parameters for Report Server.

Prerequisites:

* Before upgrading Report Server 6.0, the Insight administrator must first upgrade to Insight Server 6.0. 
* For all languages, Report Server 6.0 requires the addition of Insight.zbin to the Report Server root folder. Make sure the base/localization/<langauge>.zbin is copied and renamed to "insight.zbin". Copy it to the root of the Report Server directory.

Update the Fonts and Start-up parameters:

1. Report Server requires font setting for double byte in order to output to different languages,

   for example:

   Report Server.cfg - Add Fonts

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Parameter for Report Server 6.0 needs to be passed in the command-line for localization purposes.

   To launch the Report Server as a service with the Locale parameters:

    1. Stop the Report Server Service. 
    1. Launch a Command Prompt as an Administrator. 
    1. Navigate to the Report Server install folder. 
    1. Type the following command to start the service:     
    
       ```    
       ReportServer.exe -RegServer -Locale -en-us
       ```

To verify if the Report Server is running with the correct parameters:

1. Open up Windows Service Manager 
1. Right-click [!DNL Adobe Insight Report Server - Properties]. 
1. The path to executable will contain the parameters:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Upgrade ** **the SiteCatalyst data feed for Insight 6.0**. The filename format of the SiteCatalyst data feed for Insight 6.0 has changed.

Current filename format:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

New filename format: 

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>This change does not affect users currently deployed with the *wbench/ecom* version of the SiteCatalyst data feed.

The filename format change will allow for the full use of the Insight Start and End time declarations during log processing. This enables the process to evaluate if the contents of the file should be read, rather than filter all source files using a row by row search.

In most cases, a rename process was implemented upon receipt of the file to provide the full use of this capability. This modification provides the required naming convention by default without the need and overhead of a secondary process.

To use the new SiteCatalyst data feed:

1. Determine how the receiving process will handle the new filename format.

   The standard rename/move scripts deployed during implementation moves the files with a ".gz" extension, and only performs a rename if the filename matched the filename format with the preceding RSID.

   The new filename format:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Evaluate the defined log source paths to confirm that all files will be read.

   If you already have a rename script implemented, then you are already defining your log sources to read this new filename format.

## Fixes {#section-203f917dd6224114a1f801309c4c2cee}

* Now, the key combination to leave a workspace without saving changes has been updated to **[!UICONTROL <Ctrl> + <Backspace>]**. Previously, you voided changes and closed a workspace by pressing <Ctrl> + <Delete>.

