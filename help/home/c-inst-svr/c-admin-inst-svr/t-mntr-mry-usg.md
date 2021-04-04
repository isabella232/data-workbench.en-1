---
description: Information on assessing and monitoring the Address Space Load.
solution: Analytics
title: Monitoring Memory Usage
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
---
# Monitoring Memory Usage{#monitoring-memory-usage}

Information on assessing and monitoring the Address Space Load.

 **Monitoring the Address Space Load**

**Recommended Frequency:** Daily

The Address Space load is a measure of the fraction of the maximum Address Space that a properly configured [!DNL Insight Server] uses. Even if the configuration parameters are changed to reduce memory usage, it usually does not decrease until the [!DNL Insight Server] service is restarted.

A safety margin is built into the Address Space load maximum to account for unexpected increases in Address Space utilization. You should never deliberately cut into this safety margin. It exists for emergency situations and not for the support of functionality added to your Adobe application.

>[!NOTE]
>
>To make more Address Space available and avoid memory exhaustion errors, ensure that your operating system has the /3GB Switch enabled and that Low Fragmentation Heap is operating.

Errors logged to the [!DNL Insight Server] event data log can provide a clue that problems are developing with your Address Space load:

* “Requested X byte block is too large” errors indicate that something may be having an excessive impact on Address Space load, performance, and network bandwidth. Such large blocks can contribute greatly to Address Space usage, both by using a lot of memory and by requiring large contiguous blocks of Address Space.

  To address this problem, you can reduce the cardinality of your largest dimensions, which increases your Address Space load. If you cannot reduce the cardinality of the dimensions, you should attempt to keep the Address Space load small enough so that you can handle an unexpected increase. 
* “Memory budget exceeded” errors indicate that you might need to increase the Query Memory Limit. Memory used by queries is proportional to dimension cardinality and, in some cases, the lengths of the element names. If you increase the Query Memory Limit, you increase your total Address Space load and shrink the large dimensions.

>[!NOTE]
>
>By default, use of large pages are allowed and memory-mapped lookup is disabled. In DWB 6.7 and later, this can be changed in dataset configuration. Any changes require a Server restart.

**To assess Address Space load**

To accurately assess the Address Space load for your system, Adobe recommends reprocessing the dataset, performing some normal queries without subsequently restarting [!DNL Insight Server], and then viewing the measured Address Space load by following these steps.

If an [!DNL Insight Server] has not been reprocessed and queried significantly since it was last restarted, you should not draw conclusions from the Address Space load. 

1. In [!DNL Insight], on the [!DNL Admin] > [!DNL Dataset and Profile] tab, click the **[!UICONTROL Servers Manager]** thumbnail to open the Servers Manager workspace.
1. Right-click the icon of the [!DNL Insight Server] you want to configure and click **[!UICONTROL Detailed Status]**.
1. In the Detailed Status interface, click **[!UICONTROL Memory Status]** to view its contents. In the Address Space Load parameter, you can see the Address Space load expressed as a percentage and a parenthetical description indicating status.

   The following table presents ranges and status for Address Space load. A recommended action is listed for each range.

   |  Address Space Load (%)  | Status  | Recommended Action  |
   |---|---|---|
   |  0-15  | lean and mean  | None.  |
   |  15-33  | light  | None.  |
   |  33-66  | moderate  | None.  |
   |  66-100  | heavy  | To avoid memory exhaustion failures, do not add significant extra functionality or attempt to process more data.  |
   |  100-125  | reliability compromised  | Adjust your dataset configuration to reduce Address Space load.  |
   |  125 or greater  | failure imminent  | Adjust your dataset configuration to reduce Address Space load. You may not see the failure imminent status before failure occurs.  |

   If you see an Address Space load above 100%, you should change the configuration as soon as possible to reduce Address Space usage.
