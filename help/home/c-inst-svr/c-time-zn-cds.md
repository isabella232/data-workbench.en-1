---
description: Format instructions about time-based parameters in Insight Server.
solution: Analytics
title: Time Zone Codes
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
---
# Time Zone Codes{#time-zone-codes}

Format instructions about time-based parameters in Insight Server.

Most time-based parameters in [!DNL Insight Server] are specified in the following format:

*Month DD, YYYY HH:MM:SS TimeZone*

Example: August 13, 2013 22:30:00 EST

Time zones are expressed in a system-independent time zone format (Coordinated Universal Time) of the following format:

UTC +hhmm *dstrules*

The sign (+) can be either a plus (+) or a minus (-) sign, and *hhmm* is the offset from UTC in hours and minutes. The optional variable *dstrules* specifies a set of rules to implement Daylight Saving Time or a similar clock-shifting policy.

If you specify *dstrules*, a tab-delimited file named *< [!DNL dstrules]>* [!DNL .dst] must be present within the Dataset\TimeZone directory of either the Base profile (for configuration files that are not associated with a particular dataset) or the dataset profile (for configuration files that are dataset-specific). The file specifies a time-zone independent set of rules for Daylight Saving Time. You can have different sets of rules for different years. The [!DNL DST.dst] file provided by Adobe in the Base profile specifies the standard U.S. rules established by the Energy Policy Act of 2005 (in effect starting 2007) and the U.S. rules for prior years.

Sample time zone entries are listed below:

* U.S. Eastern Daylight Time: Time Zone = string: UTC -0500 DST 
* UTC time with no offset and no *dstrules* (corresponding to GMT): Time Zone = string: UTC -0000

When this format is used, the system time zone of [!DNL Insight Server], [!DNL Insight], and [!DNL Report] machines need not be the same as the specified time zone. In addition, all active dataset profiles on an [!DNL Insight Server] machine need not have the same time zone setting.

The following table contains the list of codes you can use to specify time zones in time-based parameters.

## Time Zone Code Table {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>If you are implementing Daylight Saving Time or a similar clock-shifting policy, you must save the [!DNL .dst] file containing the appropriate rules in the *profile name*\Dataset\Timezone directory on the [!DNL Insight Server] machine.

|  Code  | Time Zone  | Offset from GMT  |
|---|---|---|
|  gmt  | Greenwich Mean  | 0  |
|  est  | Eastern Standard  | 5  |
|  edt  | Eastern Daylight  | 5  |
|  cst  | Central Standard  | 6  |
|  cdt  | Central Daylight  | 6  |
|  mst  | Mountain Standard  | 7  |
|  mdt  | Mountain Daylight  | 7  |
|  pst  | Pacific Standard  | 8  |
|  pdt  | Pacific Daylight  | 8  |
