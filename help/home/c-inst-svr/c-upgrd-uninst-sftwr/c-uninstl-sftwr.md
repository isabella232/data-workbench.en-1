---
description: Instructions to uninstall Insight Server, Transform, or Repeater.
solution: Analytics
title: Uninstalling Your Software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
---
# Uninstalling Your Software{#uninstalling-your-software}

Instructions to uninstall Insight Server, Transform, or Repeater.

## Uninstalling Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Unregister the [!DNL Insight Server] Windows service.

    1. Open a command prompt and navigate to the bin sub-directory in the folder where you installed [!DNL Insight Server].

       Example: [!DNL C:\Adobe\Server\bin] 
    
    1. At the command prompt, execute the following command to stop and unregister it as a service under Microsoft Windows:     
    
       ```    
       InsightServer64.exe /unregserver
       ```

1. Delete the [!DNL Insight Server] installation directory.

## Uninstalling Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Use the following steps to update the [!DNL profile.cfg] file for each profile with which you were using [!DNL Transform].

    1. Open the [!DNL Profile Manager]. 
    1. Right-click the check mark next to [!DNL profile.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 
    
    1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. The [!DNL profile.cfg] window appears. 
    
    1. In the [!DNL profile.cfg] window, delete the [!DNL Transform] profile entry from the Directories vector. 
    
    1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 
    
    1. In the [!DNL Profile Manager], right-click the check mark for [!DNL profile.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*.

1. Delete the [!DNL Transform] folder from the [!DNL Profiles] folder in your [!DNL Insight Server] installation directory.

## Uninstalling Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Unregister the [!DNL Repeater] Windows service.

    1. Open a command prompt and navigate to the bin sub-directory in the folder where you installed [!DNL Repeater].

       Example: [!DNL D:\Adobe\Repeater\bin] 
    
    1. At the command prompt, execute the following command to stop and unregister it as a service under Microsoft Windows:     
    
       ```    
       InsightServer64.exe /unregserver
       ```

1. Delete the [!DNL Repeater] installation directory.
