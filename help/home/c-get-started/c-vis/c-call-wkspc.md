---
description: Callouts are windows that you add to a workspace to bring attention to a particular dimension element by creating a new visualization with a virtual selection of that element.
seo-description: Callouts are windows that you add to a workspace to bring attention to a particular dimension element by creating a new visualization with a virtual selection of that element.
seo-title: Adding callouts to a workspace
solution: Analytics
title: Adding callouts to a workspace
topic: Data workbench
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
---

# Adding callouts to a workspace{#adding-callouts-to-a-workspace}

Callouts are windows that you add to a workspace to bring attention to a particular dimension element by creating a new visualization with a virtual selection of that element.

 Data Workbench is delivered with a standard set of callout types. Because your implementation can be fully customized, the available callout types that appear in your implementation may differ from what is documented in this guide.

By default, Data Workbench provides the following callouts:

* [Annotation](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d) 
* [Blank Line Graph](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f) 
* [Blank Scatter Plot](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f) 
* [Blank Table](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f) 
* [Confidence Legend](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791) 
* [Metric Legend](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>Callouts do not function as selections (that is, they do not affect other visualizations within the workspace) unless you make a selection within the callout.

You can add or edit callout definitions by configuring the callout files stored in the *profile name*\Context\Callout folder of the [!DNL Server] installation folder. See [Configuring Callouts](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## To add an annotation callout to a visualization {#section-7b6742160b3f4aed872a09c8c023f90d}

1. Right-click the element for which you want to create a callout, then click **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** or **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. A blank window displays with a visible connection to that element.

   ![](assets/client-call.png)

   To add callouts to Graph visualizations, you need to right-click at the bottom of the visualization (the base axis) to open a menu.

   ![](assets/visualization_callout_linegraph.png)

1. Depending on your selection, complete the appropriate step:

    * For a text annotation, type or paste the desired text into the callout, then format the text as appropriate. See [Working with Text Annotations](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777). 
    * For an image annotation, paste the desired image into the callout by copying the image, then right-clicking within the callout. Click **[!UICONTROL Paste image]**. See [Working with Image Annotations](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## To add a blank table, line graph, or scatter plot callout to a visualization {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Right-click the element for which you want to create a callout and click **[!UICONTROL Add Callout]** > *< **[!UICONTROL callout type]**>*.

   The following example shows a Blank Table callout.

   ![](assets/vis_callout_blank_bar_graph.png)

1. To select a dimension, right-click **[!UICONTROL None]** and click **[!UICONTROL Change Dimension]** > *< **[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >If you change the dimension within a visualization that has a callout, the callout changes from being connected to the element of the original dimension to being connected to the entire visualization.

## To add a confidence legend callout to a visualization {#section-386d1293ddc24a0c9cccb332e20db791}

1. Right-click the element for which you want to create the callout and click **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. If desired, change the [!DNL Metric or Formula] field.

For expression syntax rules, see [Query Language Syntax](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f). See [Confidence Legends](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## To add a metric legend callout to a visualization {#section-daa6d372c22246d9827880a9d6e804d8}

1. Right-click the element for which you want to create the callout and click **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. If desired, add metrics to or remove metrics from the metric legend.

See [Metric Legends](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b). 
