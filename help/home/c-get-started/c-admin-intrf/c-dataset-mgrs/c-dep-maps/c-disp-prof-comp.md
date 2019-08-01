---
description: You can choose to display your profile’s dataset components, query model components, or workspaces, reports, menu options, and globe layers in the dependency map.
seo-description: You can choose to display your profile’s dataset components, query model components, or workspaces, reports, menu options, and globe layers in the dependency map.
seo-title: Display profile components
solution: Analytics
title: Display profile components
topic: Data workbench
uuid: 12d09387-38ec-436c-b297-bf558acb08a8
index: y
internal: n
snippet: y
---

# Display profile components{#display-profile-components}

You can choose to display your profile’s dataset components, query model components, or workspaces, reports, menu options, and globe layers in the dependency map.

 **To select the components to display**

1. Right-click within the dependency map and click **[!UICONTROL Display]**. 
1. Choose one or more of the following options to display on the map. An X appears to the left of each display option that you enable.

    * **Dataset** to display dataset components. See [Dataset Components](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293). If you choose to display the dataset components, you have the option to [!DNL Include File Blocks] on the map. See [Working with File Blocks](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc). 
    
    * **Query Model** to display query model components. See [Query Model Components](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f). 
    
    * **Workspaces and Visualizations** to display workspaces, reports, menu options, and globe layers. See [Workspaces and Visualizations](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). This option works only if the [!DNL Query Model] display option is enabled.

>[!NOTE]
>
>If the [!DNL Query Model] display option is not enabled when you choose the [!DNL Workspaces and Visualizations] display option, an error message appears.

If you cannot see all of the nodes on the map, you can move the map or zoom in or zoom out to display the entire map or to focus on a particular section. For more information about zooming, see [Zooming in Visualizations](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

When you click a node, all of the nodes that depend on that node and all of the nodes on which that node depends are highlighted and their names display.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>A highlighted path in a dependency map does not constitute a selection.

When you right-click a node, you can see identifying information about each component shown on the map and choose menu options that enable you to view more detail about the component or to edit the component. In addition, you can perform text searches and display performance information for transformations and extended dimensions. 
