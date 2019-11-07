---
description: The Attribution profile is an inherited, ready-to-drop-in profile. In combination with the Adobe SC profile and Analytics (SC/Insight) data feed, the profile can be deployed to quickly expose new attribution models across digital channels.
title: Deploying the Attribution Profile
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
---

# Deploying the Attribution Profile{#deploying-the-attribution-profile}

The Attribution profile is an inherited, ready-to-drop-in profile. In combination with the Adobe SC profile and Analytics (SC/Insight) data feed, the profile can be deployed to quickly expose new attribution models across digital channels.

 After saving the Attribution profile to the primary server, there are two additional steps necessary to integrate it into the current profile within the [!DNL Profile] directory: (1) Set up the Profile.cfg file, and (2) Declare the Required Fields.

## Setting up Profile.cfg file {#section-7531cb865d994207baba692a6fc842d7}

Like all profiles, the Attribution profile needs to be added to the [!DNL profile.cfg] file. Because the Attribution profile depends on the Adobe SC profile, the Adobe SC profile needs to be listed first in the configuration file before the Attribution profile. 

>[!NOTE]
>
>These steps will require a re-transformation of the dataset.

1. Open the [!DNL profile.cfg] file in your custom profile folder. (Open in [!DNL server\Profiles\(custom profile name)\profile.cfg]. 

1. If the Attribution profile is not listed in the configuration file, add it to the list. ![](assets/new_profile_cfg.png)

1. Make sure the **[!UICONTROL Attribution]** string is listed below the **[!UICONTROL Adobe SC]** profile string. 

1. Save the updated [!DNL profile.cfg] file and then save it to server from the Profile Manager.

## Declaring the Required Fields {#section-23d4273af0c34b7a85ae3430e2c9350e}

The Attribution profile takes predefined fields and with a series of transformations exposes those fields in new and useful ways through extended dimensions. To provide the most immediate value the Attribution profile depends on fields available with the Adobe SC profile. 

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Default Variables </th> 
   <th colname="col2" class="entry"> Field Name and Decoder Position (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marketing Channels </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Order event </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Revenue </td> 
   <td colname="col2"> x-revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Units </td> 
   <td colname="col2"> <p>x-units, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Verify that these fields are declared in the Decoder Group used to define the Adobe Analytics data source. The default decoder group is provided under [!DNL Dataset\Log Procesing\Decoding Instructions.cfg]. 
1. Verify that these fields are declared in the **[!UICONTROL Fields]** section of the [!DNL SC Fields.cfg] file. This file can be located under [!DNL Dataset\Log Processing\SC Fields.cfg].

## Attribution Additions and Troubleshooting {#section-168133a8a1a54e1281e532033878d246}

The Attribution profile added a configuration file, [!DNL 0a_Marketing Channels.cfg], which copies the value of the [!DNL x-va_closer_detail] into a new field called [!DNL x-marketing-channel], when the [!DNL x-va_instance_event] field matches "1". Both [!DNL x-va_closer_detail] and [!DNL x-va_instant_event] are decoded by default, and passed from decoding in the installed packages available when you update to version 6.2.

The [!DNL x-marketing-channel] field is then used in the Simple dimension called Marketing Channel.

>[!IMPORTANT]
>
>If you have altered your profiles by removing previously unused fields that are now being used, you will want to verify that the [!DNL x-va_closer_detail] and [!DNL x-va_instance_event] fields are being decoded and passed through for use.

If fields are missing, then you will get a message in your detailed status: 

```
<b>x-va_closer_detail</b> is not available
```

or 

```
<b>x-va_instance_event</b> is not available
```

