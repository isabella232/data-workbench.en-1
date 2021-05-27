---
description: Hierarchy views are available only when using the Site or HBX application.
title: Apply hierarchy views
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
---
# Apply hierarchy views{#apply-hierarchy-views}

Hierarchy views are available only when using the Site or HBX application.

The hierarchy view displays the pages in a website organized hierarchically by file name and sorted alphabetically. While useful for analysis itself, the hierarchy view also can be used to set up such advanced visualizations as process maps. For more information about process maps, see [Process Maps](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>If your dataset has been configured to run on multiple servers in a cluster, for this feature to work properly, your system administrator must designate which machine functions as your Central Normalization Server. For steps to do so, see the Log Processing Configuration File chapter of the *Dataset Configuration Guide*.

![](assets/vis_Table_CompareHierarchy.png)

**To enable or disable the hierarchy view**

* From any page or URI visualization, right-click an element or the label of the page dimension and click **[!UICONTROL Hierarchy View]**.

  ![](assets/mnu_Table_HierarchyView.png)

  An X is shown next to the option when the [!DNL hierarchy view] is active.

  The hierarchy is organized into website sections and pages using a tree structure. Sections (nodes) can be expanded or condensed using the + or - symbol next to the section name. Individual pages do not have a + or - symbol next to them.

  ![](assets/vis_Table_HierarchyView_Expanded.png)

## Masking Dimension Elements in a Hierarchy View {#section-e477c469934846da8d807f92fc2f3ed1}

Masking refers to selecting a subset of your data or a subset of the elements in a dimension. You mask or hide those elements that you do not want included in the analysis. Using the [!DNL Mask] menu options for hierarchy views, you select the minimum percentage of a metric that an element must have to be displayed in the visualization.

**To mask data using the [!DNL Mask] menu option**

1. Right-click an element or the label of the dimension and click **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. Under More than, click the appropriate percentage, then click the metric that you want to mask.

For example, if you click 0.1%, and then click Page Views, you are masking (hiding) any element that has less than 0.1% of the total number of pages views and displaying any element that has more than 0.1% of the total number of pages views. If you click 0%, you are masking all elements with a value of 0 (zero) for the selected metric.
