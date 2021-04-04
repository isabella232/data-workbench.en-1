---
description: Conceptual information about dataset components.
solution: Analytics
title: Dataset components
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
---
# Dataset components{#dataset-components}

Conceptual information about dataset components.

The following figure shows a dependency map whose nodes represent a dataset’s log sources, fields, transformations, and extended dimensions.

![](assets/vis_DependencyMap.png)

* A yellow-green node represents one or more log sources or a filter (such as a Log Entry Condition) defined in the dataset.

    * A node for a log source always appears furthest to the left in the map. If your dataset has a single log source, the map displays Log Source: *log source name*. If your dataset has multiple log sources, the map displays *number* Log Sources, where number is the count of log sources. For example, if you have three log sources in your dataset, your map displays 3 Log Sources. 
    
    * The map displays one Log Entry Condition node for each [!DNL log processing dataset include] file but only one Log Entry Condition node for transformation (if defined in the [!DNL Transformation.cfg] file). If the Log Entry Condition is empty, it does not display on the map.

* A gray node represents a field that is listed in the Fields parameter in a [!DNL Log Processing.cfg] or [!DNL Log Processing include] file. 

* A blue node represents a transformation. 
* A green node represents an extended dimension.

>[!NOTE]
>
>If your profile’s Dataset folder contains the file [!DNL Insight Transform.cfg], the dependency map shows the log sources, transformations, and exporters defined for use with Transform. For information about Transform, see the *Dataset Configuration Guide*.

When you enable the Include [!DNL File Blocks] display option, the map displays a single blue node for all of the transformations defined in one dataset configuration file and a single green node for all of the extended dimensions defined in one dataset configuration file. For more information about this display option, see [Working with File Blocks](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
