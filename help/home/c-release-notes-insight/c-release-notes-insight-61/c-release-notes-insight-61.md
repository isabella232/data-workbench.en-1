---
description: Data Workbench 6.1 release notes include new features, upgrade requirements, bug fixes, and known issues.
seo-description: Data Workbench 6.1 release notes include new features, upgrade requirements, bug fixes, and known issues.
seo-title: Data Workbench 6.1 Release Notes
solution: Analytics
title: Data Workbench 6.1 Release Notes
topic: Data workbench
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
---

# Data Workbench 6.1 Release Notes{#data-workbench-release-notes}

Data Workbench 6.1 release notes include new features, upgrade requirements, bug fixes, and known issues.

To view previous features and fixes based for each past release, see the [release note archives](https://marketing.adobe.com/resources/help/en_US/insight/insight_release_notes_prev.pdf).

## New Features {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.1 includes these new features: 

| Features | Description |
|--- |--- |
|64-bit Windows upgrade|The data workbench server, report server, and client components are upgraded to run only on 64-bit Windows operating systems.|
|Propensity Scoring|Scoring your audience lets you identify customer loyalty and statistically perceive who is likely to convert a sale or interact with a story or campaign. Propensity scoring now includes these visualizations to view models and show the changing correlation of selected metrics.<ul><li>The  Model Viewer examines a logistic regression model generated with Propensity Scoring, displaying the coefficient weights of each input variable (including the constant term) and their statistical error range. </li><li>Lift and Gain charts are used to evaluate the potential increase of a scored data model.</li><li>The Confusion Matrix gives four counts by the combination of Actual Positive (AP), Actual Negative (AN), Predicted Positive (PP), and Predicted Negative (PN).</li> <li>Starting with v6.1, you now have a  Save option to save propensity scores based on two types: dimensions, or dimensions and metrics.</li><li>You can now click Ctrl-Alt and drag and drop to add elements in Propensity Scoring and the  Cluster Builder. Previously to add table elements, you had to drag from the table to the Elements box.</li></ul>|
|Data workbench now in Chinese|Data workbench now supports Simplified Chinese for the client application. Data workbench also supports the  Input Method Editor (IME) as a secondary text entry process for international languages.|
|Math Functions|You can now add Mathematical functions to metrics, math transformations, and worksheet cells to further calculate datasets.|
|Statistical Callouts|Tables now offer a statistics summary call-out for metric columns. The call-out can display the mean, standard deviation, minimum and maximum values, variance, and total count for the column. It can be factored in to any selection and evaluation.|
|Correlation Matrix filter|The Correlation Matrix has been updated with a  Binary Filter to let you constrain values for one or both of the correlated metrics, allowing you to better focus your comparison. Also, you can now add Dimension elements from a Dimension table by clicking Ctrl + Alt and dragging elements to the matrix column or row to be evaluated.|
|Hide Fallout label in funnel visualization|Toggle between displaying and hiding fallout labels in a Funnel visualization by right-clicking the title and selecting  Hide Fallout.|

## Sorting Table Columns{#sorting-table-columns}

Sort table columns alphabetically or by ordinals.

To better select elements in a Dimension table, you can order the first column alphabetically or by ordinals by selecting the **[!UICONTROL Sort]** menu option.

The # character will display when a column is sorted by ordinals (the default).

**Select Sort Option**

To change sorting options between ordinal and alphabet, right-click and select **[!UICONTROL Sort]**. Click the arrow to reverse the order.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>You can sort other columns by ordinal by clicking the name of the column.

## Hide Fallout Labels in Funnel

Toggle to open fallout labels in a Funnel visualization.

The Funnel visualization identifies where a customer abandons a marketing campaign or diverts from a defined conversion path while interacting with your website or cross-channel campaign. The left side of the Funnel visualization displays the results of a visit or visitors, while the right side displays the "Fallout" of those who abandon a specified path.

![](assets/c_funnel_hide_fallout.png)

When in a **[!UICONTROL Funnel]** visualization, you can right-click the title and select **[!UICONTROL Hide Fallout]** from the menu to hide the fallout labels. 

## Known Issues {#section-ff2180c6871c413480e15fa915c253b9}

* When importing a workspace, an error message is displayed even though the import was successful.

  Workaround: Click OK to ignore the error. The workspace is imported successfully.

**Simplified Chinese Localization Issues**

* The dialog title and message displayed after clicking "Submit" when setting the target in the Scoring visualization are unreadable.

  Workaround: None. 
* When using word wrap in the Worksheet visualization, localized words are not being wrapped correctly. Extra junk characters are being added to the string.

  Workaround: None 
* Unable to launch [!DNL Insight.exe] if the installation directory is named with non-English characters.

  Workaround: Keep default names or rename using only English characters in the folder path to launch executables.
