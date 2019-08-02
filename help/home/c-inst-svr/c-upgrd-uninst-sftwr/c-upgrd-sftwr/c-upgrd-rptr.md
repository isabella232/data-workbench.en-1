---
description: Instructions to upgrade Repeater using Insight or to upgrade by copying files.
seo-description: Instructions to upgrade Repeater using Insight or to upgrade by copying files.
seo-title: Upgrading Repeater
solution: Insight
title: Upgrading Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
index: y
internal: n
snippet: y
---

# Upgrading Repeater{#upgrading-repeater}

Instructions to upgrade Repeater using Insight or to upgrade by copying files.

You can use one of the following methods to upgrade [!DNL Repeater] from Platform 4.x or later:

* If you created a connection between [!DNL Insight] and [!DNL Repeater] as described in [Creating a Connection Between Insight and Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), you can use [!DNL Insight] to upgrade [!DNL Repeater]. See [Upgrading Repeater Using Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

  -or- 

* If you could not or did not create a connection between [!DNL Insight] and [!DNL Repeater], you must copy the upgrade files directly to the [!DNL Repeater] machine. See [Upgrading Repeater by Copying Files](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Upgrading Repeater Using Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. On the [!DNL Insight] computer, copy the [!DNL bin] folder from the [!DNL Insight Server] upgrade package to the [!DNL Temp] folder in the directory where [!DNL Insight] is installed. 
1. Start [!DNL Insight]. 
1. In [!DNL Insight], on the [!DNL Admin] > [!DNL Dataset and Profile] tab, click the **[!UICONTROL Servers Manager]** thumbnail to open the Servers Manager workspace. 
1. Right-click the icon of the [!DNL Repeater] you want to upgrade and click **[!UICONTROL Server Files]**. 
1. In the [!DNL Server Files Manager], do the following to upload the upgrade files to the server:

    1. Locate the [!DNL bin] folder. 
    1. Right-click the check mark for the [!DNL bin] folder in the Temp directory and select **[!UICONTROL Save Directory to]** > *< **[!UICONTROL server name]**>*.

>[!NOTE]
>
>You will see a message indicating that this step overwrites files of the same name that exist on the server. Click **[!UICONTROL Yes]** to continue.

>[!NOTE]
>
>If you need to upload additional files to complete your [!DNL Repeater] upgrade, Adobe will provide instructions to do so.

After you upload the upgrade files to the [!DNL Repeater] machine, [!DNL Repeater] automatically restarts itself and loads the new version.

## Upgrading Repeater by Copying Files {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Open the upgrade file provided by Adobe. Most likely, this file is a [!DNL .zip] file for upgrading [!DNL Insight Server]. 
1. Go to the directory where you installed [!DNL Repeater] (for example, [!DNL D:\Adobe\Repeater]). 
1. Copy the [!DNL bin] folder within the [!DNL .zip] file and paste it in your [!DNL Repeater] installation directory to overwrite the existing [!DNL bin] folder.

>[!NOTE]
>
>If you need to upload additional files to complete your [!DNL Insight Server] upgrade, Adobe will provide instructions to do so.

After you copy the upgrade files to the [!DNL Repeater] machine, [!DNL Repeater] automatically restarts itself and loads the new version. 
