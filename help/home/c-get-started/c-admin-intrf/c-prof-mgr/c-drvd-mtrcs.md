---
description: You define new metrics (referred to as derived metrics) and edit existing metric definitions using the Metric Editor.
seo-description: You define new metrics (referred to as derived metrics) and edit existing metric definitions using the Metric Editor.
seo-title: Work with derived metrics
solution: Analytics
title: Work with derived metrics
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
---

# Work with derived metrics{#work-with-derived-metrics}

You define new metrics (referred to as derived metrics) and edit existing metric definitions using the Metric Editor.

For more information about metrics than is provided in this section and in [Query Language Syntax](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f), see the *Metric, Dimensions, and Filters Guide*.

## Create a derived metric {#section-d57b98bf0a9940daba4920ff7efc808d}

You use a [!DNL Metric Editor] to define a new metric by name, formula, and format, which is saved to the User\*profile_name*\Metrics folder for later use.

1. Open a new [!DNL Metric Editor] using the **[!UICONTROL Admin]** > **[!UICONTROL Profile]** menu option or by right-clicking the **[!UICONTROL User]** column for the folder in which you want to create the metric and clicking **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   A [!DNL Metric Editor] displays. 

1. In the Name parameter, type a name for the new metric.

   Note that spaces ( ) are allowed while underscores (_) are not. In addition, you cannot use the following symbols:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. In the Formula parameter, type an expression for the new metric. Note that filters must be defined within brackets [ ] in the expression.

   For additional metric expression syntax rules, see [Syntax for Metric Expressions](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   The following table provides sample expressions for extended metrics.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Extended Metric Name </th> 
      <th colname="col2" class="entry"> Expression </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Percent First Sessions </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessions [Session_Number="1"]/Sessions</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Conversion First Sessions </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversion [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Average Value Per Visitor </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Value/Visitors</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >When an appropriate expression is entered, the preview line displays the value of the new metric. If there is an error in the expression, the preview line displays an error message.

1. Right-click **[!UICONTROL (New)]** and click **[!UICONTROL Save]**.

   When you save the metric, a file representing the new metric is created on your computer in the Data Workbench Installation directory \User\*profile name*\Metrics folder.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

You now can use the new metric throughout the current profile by selecting it as you would any built-in metric. To change the order in which your metrics appear on the metrics menu, see [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

If you would like all users of the profile to use the metric that you created, you must publish it to the working profile using the [!DNL Profile Manager]. See [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Edit a derived metrics {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. In the [!DNL Profile Manager] or [!DNL Metrics Manager], in the *profile name* column, right-click the check mark for the metric file that you want to edit, then click **[!UICONTROL Make Local]**. 
1. Right-click the check mark for the metric file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >You also can open a [!DNL Metric Editor] by right-clicking any metric-related area within a visualization to display the metric menu. For more information, see [Working with Metric and Dimension Menus](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. In the [!DNL Metric Editor], edit and save the metric definition as necessary using Steps 2-4 in [Creating New Derived Metrics](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   If you would like all users of the profile to use the metric that you edited, you must publish it to the working profile using the [!DNL Profile Manager]. See [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

