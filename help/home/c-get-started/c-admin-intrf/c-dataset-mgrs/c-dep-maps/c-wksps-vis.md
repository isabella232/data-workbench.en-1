---
description: Conceptual information about workspaces and visualizations.
seo-description: Conceptual information about workspaces and visualizations.
seo-title: Workspaces and visualizations
solution: Analytics
title: Workspaces and visualizations
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
---

# Workspaces and visualizations{#workspaces-and-visualizations}

Conceptual information about workspaces and visualizations.

The following figure shows a dependency map whose nodes represent the workspaces, reports, menu options, and globe layers defined in the profile. This option works only if the [!DNL Query Model] display option is enabled.

>[!NOTE]
>
>If the [!DNL Query Model] display option is not enabled when you choose the [!DNL Workspaces and Visualizations] display option, an error message appears.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* A gray node represents a workspace or a report. 
* A yellow-green node represents a menu option. 
* A red node represents a workspace, report, menu option, or globe layer with a broken or circular dependency or other error.

>[!NOTE]
>
>Because the dependency map is designed to accommodate acyclic dependencies, nodes involved in circular dependencies may not display properly on the map. You can search for circular dependencies by typing “circular dependency” in the [!DNL Search] text box. For more information about the [!DNL Search] feature, see [Searching Within a Map](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

For descriptions of other nodes on the map, see [Query Model Components](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f). 
