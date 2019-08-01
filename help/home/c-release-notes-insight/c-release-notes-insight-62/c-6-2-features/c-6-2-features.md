---
description: Data Workbench 6.2 includes the following features.
seo-description: Data Workbench 6.2 includes the following features.
seo-title: Data Workbench 6.2 features
title: Data Workbench 6.2 features
uuid: bc343f7e-3d40-4e4d-822b-2825ae523afd
index: y
internal: n
snippet: y
---

# Data Workbench 6.2 features{#data-workbench-features}

Data Workbench 6.2 includes the following features.

## Upgrade Requirement {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* The Attribution profile is configured for users who have implemented the Adobe SC profile to employ the Analytics (SC/Insight) data feed. By default, the Marketing and Conversion events are employed as the default interactions evaluated in the rules-based models. See [Deploying the Attribution Profile](http://marketing.adobe.com/resources/help/en_US/insight/whatsnew/?f=c_attrib_profile_deploy) for additional information. 
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. This will only be an issue if you have modified the configuration file from the default configuration. 

* If you have deleted unused fields in the [!DNL Dataset > Log Processing > SC Fields.cfg] file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile (see [Deploying the Attribution Profile](http://marketing.adobe.com/resources/help/en_US/insight/whatsnew/?f=c_attrib_profile_deploy)).

