---
description: Process maps enable you to analyze the flow of activity between elements of a dimension.
seo-description: Process maps enable you to analyze the flow of activity between elements of a dimension.
seo-title: Process map
solution: Analytics
title: Process map
topic: Data workbench
uuid: f1db41a9-400e-467a-ba59-39831fb166af
index: y
internal: n
snippet: y
---

# Process map{#process-map}

Process maps enable you to analyze the flow of activity between elements of a dimension.

 You create process maps by dragging and dropping the elements of a dimension onto a blank two-dimensional (2D) or three-dimensional (3D) map. The elements become nodes on the map. Nodes are circles in 2D process maps and bars in 3D process maps.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>A process map gets its name from its use in analyzing the flow of activity between the steps in a process. In this type of analysis, each element on the map represents a step in the process.

Unlike path browsers, process maps can show as few or as many elements as necessary for your analysis. You choose the elements of interest and drag and drop them onto the map. Also unlike path browsers, process maps depict the flow of activity in both directions between one element and one or more other elements.

>[!NOTE]
>
>For these maps to work most effectively, you should open a color legend in the workspace. For information about using color legends with process maps, see [Activating Color Links](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). For more information about color legends, see [Color Legends](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Every process map has an associated base dimension, group dimension, level dimension, and metric, which provide keys for interpreting the data shown in the process map.

The default settings for a process map’s dimensions and metric depend on the Data Workbench application that you are using. For information about the dimensions and metrics available to you for your process maps, see the application guide for your Data Workbench application.

* **Base dimension:** When you drag and drop an element onto a process map, you are dragging and dropping an element of the base dimension. 
* **Level dimension:** Every dimension in your dataset has an associated level dimension (also referred to as a parent). The level dimension for your process map should be the same as the level dimension (or parent) for your process map’s base dimension. For example, if you drag a page (an element of the Page dimension) to the map, the corresponding level dimension would be Page View. 
* **Group dimension:** The group dimension determines how the elements of the level dimension are grouped to form the connections between nodes. For process maps, the group dimension is important for three main reasons:

    * A connection between two nodes cannot span more than one element of a group dimension. To understand this, consider an example using web data. Suppose that the base, level, and group dimensions for your process map are Page, Page View, and Session, respectively. A connection from page A to page B tells you that, during any single session, a page view of page A occurred prior to a page view of page B with no intervening page views of other pages (nodes) on the map. Note that page views of other pages of the site might have occurred between page views for pages A and B during the same session, but these pages are not shown on this map. 
    * A connection between two nodes can represent multiple elements of the group dimension. For example, there might be multiple sessions in which a page view of page A occurred prior to a page view of page B. Therefore, the connection between page A and page B represents all of the individual sessions in which a page view of page A occurred prior to a page view of page B with no intervening page views of other pages (nodes) on the map. 
    * When you make a selection based on a node within a process map, you are selecting all of the elements of the group dimension that involved that node. See [Making Selections in Visualizations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). For information about selections, see [Making Selections in Visualizations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Metric:** The size of the node for a given element is proportional to the metric’s value for that element. Larger nodes indicate greater metric values than smaller nodes.

For example, if you are using the [!DNL Site] or HBX application, you can drag, by default, elements of the Page dimension onto the process map. The size of each node is related to the quantity of sessions (defined by the Sessions metric) in which that page was viewed.

>[!NOTE]
>
>You can change the default dimensions or metric for a process map. For steps to configure a process map, see [Configuring Process Maps](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

