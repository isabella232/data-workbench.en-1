---
description: A Binary Filter in the Correlation Matrix lets you constrain values for one or both of the correlated metrics to better focus the comparison.
seo-description: A Binary Filter in the Correlation Matrix lets you constrain values for one or both of the correlated metrics to better focus the comparison.
seo-title: Binary Filter in the Correlation Matrix
solution: Analytics
title: Binary Filter in the Correlation Matrix
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
---

# Binary Filter in the Correlation Matrix{#binary-filter-in-the-correlation-matrix}

A Binary Filter in the Correlation Matrix lets you constrain values for one or both of the correlated metrics to better focus the comparison.

To set a binary filter on a Correlation Matrix:

1. From the Correlation Matrix, right-click a metric name. 
1. Select **Edit Metric Details**.

   ![](assets/correlation_matrix_binary_filter.png)

   The **[!UICONTROL Edit Correlation Metric Details]** window will open.

   ![](assets/correlation_matrix_metric_details.png)

1. Set up a Binary Filter.

   First, click the **[!UICONTROL Inactive]** setting. It will toggle to set the filter as **[!UICONTROL Active]** and display the **Comparison** and **Value** fields.

   Then, select a **[!UICONTROL Comparison]** operator and set its **[!UICONTROL Value]** to set up a filter for the selected metric.

>[!IMPORTANT]
>
>The Binary Filter for Data Workbench 6.2 has been updated with new features, requiring you to rebuild any correlation matrix with a binary filter built in previous versions.

## Adding Dimension Elements {#section-f19f4e0368ca488e92d1e28bcc24417c}

You can also add a dimension element to constrain a metric. A metric can have only one element associated with it.

![](assets/correlation_matrix_element.png)

Right-click in the workspace and select **Table**. Open a dimension with its elements and drag to the **[!UICONTROL Element]** setting in the Edit Correlation Metric Details window, or drop on a metric in the Correlation Matrix. 
