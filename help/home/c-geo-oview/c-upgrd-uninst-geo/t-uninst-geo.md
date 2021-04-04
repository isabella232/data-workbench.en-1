---
description: Steps to uninstall data workbenchGeography.
solution: Analytics
title: Uninstalling Data Workbench Geography
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
---
# Uninstalling Data Workbench Geography{#uninstalling-data-workbench-geography}

Steps to uninstall data workbenchGeography.

>[!NOTE]
>
>If the profile with which you are using data workbench [!DNL Geography] is running on a data workbench server cluster, uninstall the [!DNL Geography] profile from the master data workbench server in the cluster.

1. Use the following steps to update the [!DNL profile.cfg] file for each profile with which you were using data workbench [!DNL Geography].

    1. Open the [!DNL Profile Manager]. 
    1. Right-click the check mark next to [!DNL profile.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 
    
    1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL profile.cfg] window appears. 
    
    1. In the [!DNL profile.cfg] window, delete the [!DNL Geography] profile entry from the [!DNL Directories] vector. 
    
    1. If you have been using a data service, delete the [!DNL IP Geo-intelligence] or [!DNL IP Geo-location] profile entry from the [!DNL Directories] vector. 
    
    1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 
    
    1. In the [!DNL Profile Manager], right-click the check mark for [!DNL profile.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*.

1. Delete the Geography folder from the Profiles folder in your data workbench server installation directory.
1. If you have been using a data service, delete the IP Geo-intelligence or IP Geo-location folder from the Profiles folder in your data workbench server installation directory.
1. Delete the Geography folder from the Lookups folder in your data workbench server installation directory.
1. If you have been using a data service, delete the IP Geo-intelligence or IP Geo-location folder from the Lookups folder in your data workbench server installation directory.
1. If you created new terrain images, delete the [!DNL Terrain Images.cfg] file from the Components folder in your data workbench server installation directory.
