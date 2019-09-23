---
description: The Insight Server (InsightServer64.exe) enables you to define custom dimensions from event data or lookup data.
seo-description: The Insight Server (InsightServer64.exe) enables you to define custom dimensions from event data or lookup data.
seo-title: About Extended Dimensions
solution: Analytics
title: About Extended Dimensions
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
---

# About Extended Dimensions{#about-extended-dimensions}

The Insight Server (InsightServer64.exe) enables you to define custom dimensions from event data or lookup data.

 Any custom dimensions that you define are referred to as extended dimensions. You can use them to create visualizations, build extended metrics, or perform analysis to understand the operations and issues associated with your business channel. You can define several types of extended dimensions in the [!DNL Transformation.cfg] file or in [!DNL Transformation Dataset Include] files.

An extended dimension represents a relationship between log field values and a parent dimension. A parent dimension can be any user-defined countable dimension. See [Countable Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). You specify the parent when defining the dimension in the [!DNL Transformation.cfg] file or a [!DNL Transformation Dataset Include] file. A dimension's parent is the same as its level. For example, if you define a dimension with a parent of Session, then that dimension is a session-level dimension.

>[!NOTE]
>
>The log field values can come from the inherent values available in the log ( [!DNL .vsl]) files or other event data sources or from extended log fields created through the use of transformations.

To add an extended dimension to a visualization, you access it from the Extended list within the [!DNL Select Dimension] menu. For example, to add an extended dimension to a graph visualization, you would right-click within the workspace and click **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *< **[!UICONTROL dimension name]**>*. If you would like to organize the list of your extended dimensions within the data workbench interface, you can move the extended dimensions into subfolders that you create. See the Administrative Interfaces chapter of the *Data Workbench User Guide*. If you do this, the subfolders' names also appear in the menu, as in Add Visualization > Graph > Extended > <*subfolder name*> > <*dimension name*>.

To see all the dimensions that have been defined for your dataset profile and the buffer size for each, open the [!DNL Detailed Status] interface in data workbench and click **[!UICONTROL Performance]**, then **[!UICONTROL Dimensions]** to expand the nodes. The buffer size, which controls query times, is expressed in MB. For more information about the [!DNL Detailed Status] interface, see the Server Administration and Installation guide. 
