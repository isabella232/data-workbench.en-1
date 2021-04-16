---
description: Conceptual information about subsets.
title: Understanding subsets
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
---
# Understanding subsets{#understanding-subsets}

Conceptual information about subsets.

When using a subset, please keep the following things in mind:

* All of your benchmarks now relate to your subset, not to the entire dataset, which is much more useful when analyzing a specific subset. See [Understanding Benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914). 
* Using a subset affects all of your workspaces because the subset is applied globally to Data Workbench. 
* Subsets affect only metrics and denormal dimensions, not normal dimensions. 
* When using [!DNL Report], subsets do not affect the data in reports published for others to view. 
* Once applied, your subset is in effect for all subsequent work in the profile, including the next time that you open this instance of Data Workbench, until you remove it. 
* The only place that indicates that a subset has been applied is the context menu that you reach by right-clicking within a workspace.

  ![](assets/mnu_Subset.png)

* You must be working online to change or remove a subset. If you are working offline and have applied a subset, you cannot view results from the entire dataset. See [Working Offline and Online](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

  >[!NOTE]
  >
  >The size of your subset is limited to the amount of data in your filter that resides on a single Data Workbench server. Therefore, if your dataset spans a Data Workbench server cluster, data for your subset comes from only one Data Workbench server in the cluster.

A user at a large retailer wants to create a subset (local cache) of one particular work week of data and then run queries only on that week of data. To do this, the user creates a subset for the days of interest.

The following example shows you a bar graph of Visitors over time and a Traffic metric legend. The first figure contains no selections: all of the data in the dataset is represented. The second figure shows data for a subset of Days = {...} by Visitors, in which Days is based on a selection of the elements April 1st through April 5th in the Day dimension.

![](assets/client-sub1.png)
