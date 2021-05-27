---
description: Latency table visualizations are tables that include a latency dimension, which is a type of derived dimension that measures the time that has elapsed since a particular event occurred.
title: Latency tables
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
---
# Latency tables{#latency-tables}

Latency table visualizations are tables that include a latency dimension, which is a type of derived dimension that measures the time that has elapsed since a particular event occurred.

 You define the event by making selections within one or more visualizations and setting those selections as the event using the Set Event context menu option. Latency tables are especially useful for tracking activity related to a campaign or to a particular customer order in which you are looking for a time correlation.

In [!DNL Site], latency tables provide information about the visitor sessions that occurred as many as seven days before or after the event, but you can configure latency tables to provide information about different countable and time dimensions. See [Configuring Latency Tables](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Elements of the parent dimension, such as a session, which are part of the specific event that you selected, have a latency of zero. All other elements are assigned latencies that reflect the distance (in the appropriate time dimension) from the event.

The following example illustrates how you might use the latency table.

**Identify value events in relation to a campaign**

Let’s say you want to track the activity of customers during the seven days before and after they responded to a particular advertising campaign. To view the latency for a particular advertising campaign, you would set the campaign of interest as the event for the latency table.

Latency in the workspace below is based on selection of Campaign 11566 (the sessions in response to this campaign).

![](assets/vis_Latency.png)

A latency of “+0 days” identifies the sessions in response to Campaign 11566, as well as all other sessions for those same customers that occurred on the same day.

A latency of “-2 days” identifies the sessions for those same customers that occurred two days before the customers responded to the campaign.

A latency of “+7 days” identifies the sessions for those same customers that occurred seven days after they responded to the campaign.

In addition to the procedures listed in the following sections, you can perform all of the same tasks that you can perform in a table, such as sort elements, mask elements, add a series legend, export data, and so on. For more information, see [Tables](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Create a latency table {#section-31a03031d9854ef7acc2462d4f37678d}

To create a latency table, you begin by making a selection, then setting that selection as the event for which you want to track latency.

1. Right-click within a workspace and open the desired visualization(s), which must be based on the countable dimension used to configure your latency table.

   For example, in [!DNL Site] the visualization(s) would need to be sessions-based. 

1. Open a blank latency table. 
1. Make a selection in your workspace. 
1. Right-click within the latency table and click **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Events that you select do not persist unless you save the selections as a latency dimension. For steps, see [Reusing a Latency Dimension](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Reuse a latency table {#section-05f741169d204213b6537dce553e4f73}

If you want to use the same latency table again, you can save the latency table locally or if you have the proper permissions you can save it to the server for all users of a particular profile to access.

**To save the latency table for use in other workspaces**

1. Right-click the top border of the visualization and click **[!UICONTROL Save]**. The [!DNL Save] window appears. The default save location is the User\*profile name*\Work folder. 
1. In the [!DNL File name] field, type a descriptive name for the visualization and click **[!UICONTROL Save]**.

**To retrieve the saved latency table**

1. Right-click within the workspace and click **[!UICONTROL Open]** > **[!UICONTROL File]**. The [!DNL Open Visualization] window appears. 
1. Navigate to the latency table that you saved. 
1. Select the latency table visualization file ( [!DNL *.vw]) and click **[!UICONTROL Open]**.

## Reuse a latency dimension {#section-29c6483bf9ba476fb1c24ad1df253f46}

If you want to use the same latency dimension again, you can save the latency dimension locally or if you have the proper permissions you can save it to the server for all users of a particular profile to access.

Any latency dimensions that you create are saved in the profile’s Dimensions directory and are available in the [!DNL Change Dimension] drop-down list within Data Workbench.

**To save the latency dimension for use in other workspaces**

1. Right-click the [!DNL Latency] column label or one of its elements and click **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] window appears. 
1. Select or create the appropriate sub-directory within the Dimensions directory. 
1. In the [!DNL File name] field, type a descriptive name for the dimension (for example, [!DNL Latency for Campaign 11565.dim]) and click **[!UICONTROL Save]**.

**To retrieve the saved latency dimension**

1. Right-click within the workspace and click **[!UICONTROL Open]** > **[!UICONTROL File]**. The [!DNL Open Visualization] window appears. 
1. Navigate to the latency visualization that you saved in the User\*profile name*\Dimensions folder. 
1. Select the latency dimension file ( [!DNL *.dim]) and click **[!UICONTROL Open]**.

## Export to Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

For information about exporting windows, see [Exporting Window Data](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Export to a TSV file {#section-fd921f351c994ed0a94f63d3bd5b5a87}

For information about exporting windows, see [Exporting Window Data](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
