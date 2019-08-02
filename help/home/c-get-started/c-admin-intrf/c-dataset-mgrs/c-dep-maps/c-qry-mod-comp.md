---
description: Conceptual information about query model components.
seo-description: Conceptual information about query model components.
seo-title: Query model components
solution: Analytics
title: Query model components
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
index: y
internal: n
snippet: y
---

# Query model components{#query-model-components}

Conceptual information about query model components.

The following figure shows a dependency map whose nodes represent a query model’s metrics, derived dimensions, and filters defined in the Dimensions, Metrics, and Filters folders within the profile as well as the extended dimensions defined in the dataset that relate to them in some way.

![](assets/vis_DependencyMap_QueryModel.png)

* A yellow-green node represents a filter. 
* A purple node represents a metric. 
* A blue-green node represents a derived dimension. 
* A green node represents an extended dimension (defined in the dataset). 
* A red node represents a metric, derived dimension, or filter with a broken or circular dependency or other error.

>[!NOTE]
>
>Because the dependency map is designed to accommodate acyclic dependencies, nodes involved in circular dependencies may not display properly on the map. You can search for circular dependencies by typing “circular dependency” in the [!DNL Search] text box. For more information about the [!DNL Search] feature, see [Searching Within a Map](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

