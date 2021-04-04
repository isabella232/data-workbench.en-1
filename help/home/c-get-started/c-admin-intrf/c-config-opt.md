---
description: The Configuration option opens your Insight.cfg file, which controls your connections to various servers.
solution: Analytics
title: Configuration option
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
---
# Configuration option{#configuration-option}

The Configuration option opens your Insight.cfg file, which controls your connections to various servers.

 ![](assets/cfg_Workstation.png)

**To edit the Insight.cfg file**

1. In the [!DNL Insight.cfg] window, modify the parameters as desired. For detailed descriptions of the parameters in the [!DNL Insight.cfg] file, see [Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b). 
1. To save your configuration settings, right-click **[!UICONTROL Insight.cfg (modified)]** at the top of the window and click **[!UICONTROL Save as Insight.cfg]**.

**To add new servers**

1. In the [!DNL Insight.cfg] window, right-click **[!UICONTROL Servers]** and click **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Complete or modify the server parameters to provide Data Workbench with access to the desired server. For detailed descriptions of the parameters in the [!DNL Insight.cfg] file, see [Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b). 
1. Repeat Step 1 and Step 2 for each server to which you want to configure a connection. 
1. To save your configuration settings, right-click **[!UICONTROL Insight.cfg (modified)]** at the top of the window and click **[!UICONTROL Save as Insight.cfg]**.

Data Workbench attempts to connect to the server(s) using the settings that you have specified. If a connection is established, a green node appears in the [!DNL Servers Manager] as shown below. If Data Workbench cannot connect to the server, a red node appears.

![](assets/vis_SysStat_RedGreenDots.png)
