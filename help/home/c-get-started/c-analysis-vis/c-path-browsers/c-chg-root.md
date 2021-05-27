---
description: You can change a path browser’s root by either designating a displayed element as the root or adding a new element to the visualization.
title: Change the path browser's root
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
---
# Change the path browser's root{#change-the-path-browser-s-root}

You can change a path browser’s root by either designating a displayed element as the root or adding a new element to the visualization.

>[!NOTE]
>
>You cannot set a start or end node as the root of a path browser.

**To set the root of a path browser**

* Right-click the desired element and click **[!UICONTROL Set as root]**.

**To add a new element to the path browser**

1. Open a graph or table showing the dimension whose elements you want displayed on the path browser.

   For example, if you are working with website data, open a page graph or table and identify the page that you want to set as the root. 

1. Press Ctrl+Alt and drag the desired element to the root position on the path browser.

   >[!NOTE]
   >
   >You can change the base dimension associated with a path browser by dragging an element of the desired dimension to the path browser. This element becomes the new root of the path browser, and the label in the top left corner of the path browser changes to reflect the dimension for this element.

   For example, suppose that you create a page path browser showing the Sequence of Pages for each Session. If you were to drag an element of the Search Term dimension to the path browser, the search term element would become the new root, and the label would now show the Sequence of Search Terms for each Session.

   >[!NOTE]
   >
   >Dragging an element to a path browser may change the base dimension associated with the path browser, but it does not change the level dimension, group dimension, or metric. Therefore, you must exercise caution in choosing a base dimension that makes sense when used with the path browser’s level dimension, group dimension, and metric. To change the level dimension, group dimension, or metric, you must edit the path browser’s [!DNL *.vw] file in a text editor such as Notepad. See [Configuring Path Browsers](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
