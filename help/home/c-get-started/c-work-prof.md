---
description: Data Workbench downloads profiles to your machine.
title: Profiles
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
---
# Profiles{#profiles}

Data Workbench downloads profiles to your machine.

If you are loading a profile for the first time, you must have a network connection to the [!DNL Data Workbench server] and be working online so that Data Workbench can download the necessary files from the [!DNL Data Workbench server].

Downloading the profile might take several minutes. You should not start working with the profile until the Data Cache begins to fill, but you do not have to wait until it is full. You can track the progress of the data cache, the progress of the profile synchronization, and the date and time of the most recently processed data, by looking at the status bars as the profile loads.

>[!NOTE]
>
>You do not see data in visualizations that you add until the data cache begins to fill.

The next time that you load the profile, updates to the profile and its data are downloaded only if you have a network connection to the [!DNL Data Workbench server] and are working online. If you are working offline, the profile and its data are loaded from your machine’s cache. In this case, you are viewing the version of the profile and data that was downloaded the last time that you worked online with the profile. For more information about working online versus offline, see [Working Offline and Online](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

When you need to change your profile (using the [!DNL Profile Manager] or the [!DNL Server Files Manager]), you should work online to ensure that you have the most up-to-date version of the profile. For more information about the [!DNL Profile Manager] and the [!DNL Server Files Manager], see [Administrative Interfaces](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

If you are unable to access or load a profile, you may need to confirm the following:

* You have a network connection to the [!DNL Data Workbench server] machine on which the profile resides. 
* You have the appropriate permissions to access the profile.

For assistance, contact your system administrator.

## Loading or switching profiles {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Launch Data Workbench. 
1. In the side bar, click the profile name and click **[!UICONTROL Switch Profile]** > *< **[!UICONTROL profile name]**>*, where *profile name* is the profile with which you want to work.

   ![](assets/sidebar_profile.png)

If this is your first time loading the selected profile, it may take several minutes to download enough data to populate a visualization.

## Accessing a profile on a cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench users who access a profile running on a

ata workbench server cluster identify only the master Data Workbench Server in the Data Workbench configuration file ( [!DNL Insight.cfg]). From the perspective of the Data Workbench user, the profile is accessible on only one Data Workbench Server (the master Data Workbench Server). However, query requests from analysts can be directed to any of the Data Workbench Servers in the cluster.

For more information about profiles running on a Data Workbench Server cluster, see the *Server Products Installation and Administration Guide*.
