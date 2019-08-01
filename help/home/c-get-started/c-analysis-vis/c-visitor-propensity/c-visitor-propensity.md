---
description: Propensity scoring lets you define customers based on their possibility of a successful conversion or completion of a specified event. It allows you to maximize the potential impact of efforts before executing a process or directing a campaign.
seo-description: Propensity scoring lets you define customers based on their possibility of a successful conversion or completion of a specified event. It allows you to maximize the potential impact of efforts before executing a process or directing a campaign.
seo-title: Propensity Scoring
solution: Analytics
title: Propensity Scoring
topic: Data workbench
uuid: 6a9ac0a2-4e8e-437b-bad6-a9dccbefec6c
index: y
internal: n
snippet: y
---

# Propensity Scoring{#propensity-scoring}

Propensity scoring lets you define customers based on their possibility of a successful conversion or completion of a specified event. It allows you to maximize the potential impact of efforts before executing a process or directing a campaign.

## The Value of Propensity Scoring {#section-c51ece66effc42de9b754f0f46027c1b}

Propensity scoring lets you perform data discovery to identify hidden behaviors or patterns that exists across your data. Specifically, propensity scoring helps you identify clusters of similar customers using more focused and objective means rather than simple segmentation or filtering. In addition, propensity scoring lets you set up predictive capabilities to identify behavior for your company's high-value customer.

Once you have identified the high-value audience, you can then engage them for the greatest effect. For example, if you are Business to Business company, you may have sales call leads that allow you to then score the leads and identify their likelihood to convert offline. Because every lead increases costs, creating an incentive to identify prospective customers with the highest likelihood of converting a sale is the most effective and the least expensive way to focus your resources.

Propensity scoring provides the ability to identify those factors that are most predictive of a particular score or to increase the likelihood of an event taking place, but it can also be applied to answer specific questions: Will the customer convert? Will the customer respond to an email? Will the customer repurchase? Propensity scoring lets you answer these questions and identify visitors with an inclination for action that can then be set up and scored.

In addition, you can use filters to define a subset of visitors to be scored using the optional **[!UICONTROL Training Filter]** feature. If no filter is applied, then all visitors are targeted for scoring.

## Features of the Propensity Scoring Visualization {#section-28413bc7d33b42c59cecb427c1c5a3fa}

To open the Propensity Scoring Visualization, click **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

The Propensity Scoring Visualization includes these features accessible from its toolbar:  

|  Toolbar Feature  | Description  |
|---|---|
|  Go  | Click to run the scoring process after setting up parameters.  |
|  Reset  | Clear all settings in the visualization.  |
|  Load  | Loads a previously created ScoreDim that allows you to change and/or rebuild the scoring model.  |
|  Save  | Save the Propensity scoring visualization as a Dim file to be accessed and opened as needed.  |
|  Submit  | Submit scoring task for server-side processing.  |
|  Options  |Set the Training Filter to limit the subset of visitors. The default filter is **[!UICONTROL Train on Everyone]**, but you can change it by making workspace selections or building a filter using the **[!UICONTROL Filter Editor]**.  |
|  Set Target  | Set the Dependent Variable.  |
|  Metric  | Add Metrics as Independent Variables.  |
|  Elements  | Drag Dimension elements using the <Ctrl> + <Alt> keys from Dimension tables.  |

**See also**:

1. The [Gain and Lift charts](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). These views can be opened from a complete scoring model or from [!DNL Add Visualization> Predictive Analytics > Scoring.] 

1. The [Model Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). These views can be opened from a complete scoring model or from [!DNL Add Visualization> Predictive Analytics > Scoring.] 

1. The [Complex Filter Description](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) feature.

## Using the Propensity Scoring Visualization {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Define one or more filters to define the visitor population for scoring**. This optional **[!UICONTROL Training Filter]** lets you target visitors based on selected criteria. If no training filter is applied, then all visitors are targeted for scoring. If the Training Filter is set, then the scoring result is meaningful to the defined visitor population, although each visitor will still be given a score. 

* **Identify the positive visitors**. To define the dependent variable to specify a target filter identifying the positive visitors that match the desired outcome. This can be as simple as Revenue > $10, or a much more complex filter. 
* **The Target filter is not allowed to be the same as the Training filter**. Logically, the Target Filter should be an addition to the Training Filter, resulting in a positive subset of the visitor population to be scored. 
* **Select variables of interest (independent variables) as inputs to the Propensity Scoring algorithm**. These can be Metrics or individual elements of a Dimension. Propensity Scoring will start preprocessing just as in [Visitor Clustering](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). The system begins capturing a certain amount of samples that match the definition of the previously set training filter (if any). Currently, the sample size is set as 10% of scoring population (defined by training filter), with a minimum of 20,000 and maximum of 100,000, and is bound to the scoring population size. 

* A Score Dimension has elements ranging from 0% to 100% that determines the likelihood of the visitors matching the Target variable.

