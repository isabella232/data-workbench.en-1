---
description: You can select a path within a path browser to create filters that include data associated with the elements in the path.
solution: Analytics
title: Select a path
topic: Data workbench
uuid: 3131df2f-674f-44b8-9006-d8cb1ecf3874
exl-id: c560dfd0-ccaf-4a60-88a1-29a33f8aa014
---
# Select a path{#select-a-path}

You can select a path within a path browser to create filters that include data associated with the elements in the path.

 When you select a path of base dimension elements within a path browser, you are selecting data for the corresponding elements of the level dimension.

For example, suppose that you have created a path browser showing pages of a website. Each page is an element of the Page dimension, and the level dimension for Page is Page View. When you select a path of pages in a path browser, you are selecting data for the page views associated with those pages.

>[!NOTE]
>
>You can change the default level dimension for a path browser. For instructions to configure a path browser, see [Configuring Path Browsers](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

1. Click an element in the path browser to extend the displayed path to the left or right of the root.
1. Right-click the desired element and click **[!UICONTROL Select path]**. The selected path is outlined in white.

   >[!NOTE]
   >
   >You cannot select a start or end node.

1. Repeat Step 1 for each element that you wish to add to the path.

   For example, if you are working with website data, you could select a path of pages on your website.

   ![](assets/client-path.png)

   This path constitutes a selection, and all other open visualizations in the workspace (including legends) update to display data associated with the path created by the selected elements. See [Making Selections in Visualizations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
