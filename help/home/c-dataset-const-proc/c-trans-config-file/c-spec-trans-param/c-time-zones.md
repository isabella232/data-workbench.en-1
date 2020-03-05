---
description: The Time Zone parameter in the Transformation.cfg file controls time dimensions, time conversions (for example, defining the x-local-timestring field), and formatting of all local times in the dataset profile.
solution: Analytics
title: Time Zones
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
---

# Time Zones{#time-zones}

The Time Zone parameter in the Transformation.cfg file controls time dimensions, time conversions (for example, defining the x-local-timestring field), and formatting of all local times in the dataset profile.

>[!NOTE]
>
>The Time Zone parameter does not affect system-level functionality such as timestamps in status and event logs, which are expressed in system local time.

The Time Zone parameter supports a system-independent time zone format ("Coordinated Universal Time") of the following format:

Time Zone = string: UTC +hhmm dstrules

The sign (+) can be either a plus (+) or a minus (-) sign, and *hhmm* is the offset from UTC in hours and minutes. The optional variable *dstrules* specifies a set of rules to implement Daylight Saving Time or a similar clock-shifting policy.

If you specify *dstrules*, a tab-delimited file named [!DNL dstrules .dst] must be present within the dataset profile's Dataset\TimeZone subdirectory. The file specifies a time-zone independent set of rules for Daylight Saving Time. You can have different sets of rules for different years. The [!DNL DST.dst] file provided by Adobe in the Base profile specifies the standard U.S. rules established by the Energy Policy Act of 2005 (in effect starting 2007) and the U.S. rules for prior years.

Sample Time Zone entries are listed below:

* U.S. Eastern Daylight Time: Time Zone = string: UTC -0500 DST 
* UTC time with no offset and no dstrules : Time Zone = string: UTC -0000

When this format is used, the system time zone of data workbench server, data workbench, and [!DNL Report] machines need not be the same as the specified time zone. In addition, all active dataset profiles on a data workbench server machine need not have the same time zone setting.

Adobe does not recommend running more than one dataset profile on a single data workbench server machine or data workbench server cluster.

Data workbench users will see data in the dataset profile's time zone instead of their system time zone. Adobe recommends that the system time zone for a data workbench server machine be the same as the time zone used in its datasets.

>[!NOTE]
>
>You can specify a Time Zone parameter in the [!DNL Log Processing.cfg] file, where it is used for time conversions during log processing. For information about the Time Zone parameter in the [!DNL Log Processing.cfg] file, see [Log Processing Configuration File](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

