---
description: Upgrading server components for Data Workbench 6.2 and 6.2.2.
seo-description: Upgrading server components for Data Workbench 6.2 and 6.2.2.
seo-title: DWB Server upgrade  6.1 to 6.2
title: DWB Server upgrade  6.1 to 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
---

# DWB Server upgrade: 6.1 to 6.2{#dwb-server-upgrade-to}

Upgrading server components for Data Workbench 6.2 and 6.2.2.

## Upgrade Issues for 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* The Attribution profile is configured for users who have implemented the Adobe SC profile to employ the Analytics (SC/Insight) data feed. By default, the Marketing and Conversion events are employed as the default interactions evaluated in the rules-based models. See [Deploying the Attribution Profile](http://marketing.adobe.com/resources/help/en_US/insight/whatsnew/?f=c_attrib_profile_deploy) for additional information. 
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. This will only be an issue if you have modified the configuration file from the default configuration. 
* If you have deleted unused fields in the [!DNL Dataset > Log Processing > SC Fields.cfg] file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile (see [Deploying the Attribution Profile](http://marketing.adobe.com/resources/help/en_US/insight/whatsnew/?f=c_attrib_profile_deploy)).

## Upgrade Issues for 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* The **[!UICONTROL Browsers]** and **[!UICONTROL Operating Systems]** lookup files will not be updated within the legacy **[!UICONTROL Traffic]** profile (for example, [!DNL Lookups\Traffic\Browsers.txt)]. Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information. 
* Data Workbench 6.2.1 will be the last release to provide a download of the 32-bit client application. All future client application downloads will be 64-bit and continue to require Windows 7 or newer. Memory limitations of the 32-bit application are addressed with the introduction of the 64-bit application beginning with the 6.1 release.

>[!NOTE]
>
>The 32-bit version of the Data Workbench client application may experience potential issues related to memory limitations when running predictive models using the clustering and scoring features.

