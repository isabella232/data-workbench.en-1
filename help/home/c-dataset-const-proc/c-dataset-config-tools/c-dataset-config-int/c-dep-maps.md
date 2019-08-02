---
description: Dependency maps enable you to visualize and manage the configuration of the components of your profile.
seo-description: Dependency maps enable you to visualize and manage the configuration of the components of your profile.
seo-title: Dependency Maps
solution: Analytics
title: Dependency Maps
topic: Data workbench
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
index: y
internal: n
snippet: y
---

# Dependency Maps{#dependency-maps}

Dependency maps enable you to visualize and manage the configuration of the components of your profile.

* **Dataset components:** Log sources, filters, fields, transformations, and extended dimensions defined in your dataset's [!DNL Log Processing.cfg], [!DNL Transformation.cfg], and [!DNL dataset include] files. 

* ** Query model components:** Metrics, dimensions, and filters defined in the Dimensions, Metrics, and Filters folders. 
* **Workspaces and visualizations:** Workspaces, reports, menu options, and globe layers.

For more information about working with query model components, workspaces, and visualizations in dependency maps, see the *Data Workbench User Guide*.

Profile components are represented by colored dots (nodes) in the map. The lines connecting the nodes depict dependencies, that is, how the components relate to one another. A line between two nodes means that an output of the node on the left is an input of the node on the right, that is, the right node depends on the left node.

## Displaying Dataset Components {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Right-click within the dependency map and click **[!UICONTROL Display]**. 
1. Choose **[!UICONTROL Dataset]**. An X appears to the left of [!DNL Dataset].

For more information about the other display options see the *Data Workbench User Guide*.

The following figure shows a dependency map whose nodes represent a dataset's log sources, fields, transformations, and extended dimensions.

![](assets/vis_DependencyMap.png)

* A yellow-green node represents one or more log sources or a filter defined in the dataset. A node for a log source always appears furthest to the left in the map. 
* A gray node represents a field that is listed in the Fields parameter in a [!DNL Log Processing.cfg] or [!DNL Log Processing Include]file. 

* A blue node represents a transformation. 
* A green node represents an extended dimension.

>[!NOTE]
>
>If your dataset has a single log source, the map displays Log Source: *log source name*. If your dataset has multiple log sources, the map displays *number* Log Sources, where number is the count of log sources. For example, if you have three log sources in your dataset, your map displays 3 Log Sources.

If you cannot see all of the nodes on the map, you can move the map or zoom in or zoom out to display the entire map or to focus on a particular section. For more information about zooming, see the Working with Visualizations chapter of the *Data Workbench User Guide*.

When you click a node, all of the nodes that depend on that node and all of the nodes on which that node depends are highlighted and their names display.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>A highlighted path in a dependency map does not constitute a selection.

When you right-click a node, you can see identifying information about each component shown on the map and choose menu options that enable you to view more detail about the component or to edit the component. In addition, you can perform text searches and display performance information for transformations and extended dimensions.

For information about these functions for dependency maps, see the Administrative Interfaces chapter of the *Data Workbench User Guide*. 
