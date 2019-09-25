---
description: Set up insight.zbin file to set the language of the client application.
seo-description: Set up insight.zbin file to set the language of the client application.
seo-title: Setting up Localized Languages
title: Setting up Localized Languages
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
---

# Setting up Localized Languages{#setting-up-localized-languages}

Set up insight.zbin file to set the language of the client application.

## Update the data workbench server components {#section-5d07a081befc4eaa8fdf7fea904e0d48}

The administrator must first complete these tasks to update these server components:

1. **Update to data workbench server 6.x.** You need to update the data workbench server for localization by updating the [!DNL base\localization\*.zbin] file. This [!DNL insight.zbin] file will then be copied to the client.

   An [!DNL insight.zbin] file is included in the installation folder alongside the [!DNL insight.exe] file. If you connect to a server that doesn't provide you with language-specific [!DNL .zbin] files, then data workbench will proceed to use this file.

   The backup [!DNL insight.zbin] file can be provided in any language. As a result, if you use data workbench in Chinese and connect to a server that doesn't support this language, then your data workbench client will still be in Chinese, even if the server changes your base profile and removes your [!DNL .zbin] files from the [!DNL Base/Localization] folder. 

1. **Update the data workbench report server.** The [!DNL insight.zbin] at the root folder of data workbench report server will be in English by default. As the administrator, you will be required to select and copy the [!DNL .zbin] file from the updated report server package and place it in the root directory of the data workbench report server. Like the client, the report server also requires the proper arguments for the selected language, such as [!DNL Insight.exe -zh-cn]

    1. Stop the report server services. 
    1. Copy the [!DNL Localization] folder from the new report server package. 
    1. From the [!DNL Localization] folder, copy the [!DNL Insight.zbin] file and place it in the root directory of the report server where the [!DNL Insight.exe] is located. 
    
    1. Add any required arguments, such as [!DNL insight.exe -zh-cn] 
    1. Restart the report server.

## Update the data workbench client {#section-9653d3fcaf2a4337a97b685857e7aeac}

After updating the server, follow these steps to update each client.

1. To make sure the client does not get updated from the server during this update, set your [!DNL Insight.cfg] argument to False. 

   ```
   Update Software = bool: false
   ```

1. Restart the client. 
1. Navigate to the Software and Docs profile (SoftDocs profile) and download the required **[!UICONTROL insight.zbin]** file from the client package: [!DNL Software\Insight Client\Insight_6.1.zip] 

1. Move the [!DNL insight.zbin] file to the folder where [!DNL insight.exe] is located. 

1. To make sure that the client files now gets updated from the server, change the [!DNL Insight.cfg] file argument to True: 

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Your client will synchronize with the server and you will see a message stating that it is updating. At the conclusion of the download, you will get a message asking if you want to restart your client.

1. Click **OK** to restart the client.

If you get the following message, then it means the [!DNL zbin] file was not placed in the same location as the [!DNL Insight.exe]. 

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Localized Splash Screens**

Data workbench looks for the following splash screen files:

* English (default): [!DNL Base/Images/<version_product> Splash.png] 
* Chinese (when started with -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

If a splash screen is requested but missing, data workbench will access the English splash screen by default.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

