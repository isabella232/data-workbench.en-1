---
description: Statistical correlations measure meaningful relationships to identify opportunities through advanced data mining.
seo-description: Statistical correlations measure meaningful relationships to identify opportunities through advanced data mining.
seo-title: Correlation Matrix
solution: Analytics
title: Correlation Matrix
topic: Data workbench
uuid: caff165f-3952-41e9-9a9e-ef03517f6f29
index: y
internal: n
snippet: y
---

# Correlation Matrix{#correlation-matrix}

Statistical correlations measure meaningful relationships to identify opportunities through advanced data mining.

 Employing the [Pearsons correlation coefficient](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c), the Correlation Matrix furnishes you with relevant information to better identify the next steps in a marketing campaign, to improve site design, or to continue in-depth customer analysis for additional correlation dependencies.

## Building a Correlation Matrix {#section-87ed12ccc1af4196a1b6534e621c4cbb}

The Correlation Matrix compares metrics over a countable or non-countable dimension. The matrix can then be modified to highlight correlations within the visualization through color picking or to render it as a text map, heat map, or both.

1. Open a Correlation Matrix.

   Right-click [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. The dimension table will open.

   ![](assets/correlation_matrix_2.png)

   Select a dimension, such as [!DNL Time] > [!DNL Day of the Week] from this menu. The correlation table will open with the dimension identified in the corner of the matrix and its associated metric placed in the row and column. For the Day of the Week dimension, **[!UICONTROL Visits]** is the associated metric.

   ![](assets/correlation_matrix_1.png)

   The correlation is 1.000 because you are comparing a metric against itself (which reflects a perfect, but unusable, correlation.) 

1. Change one of the metrics.

   Right-click and select **[!UICONTROL Change Metric]** to change a metric in either the row or column. This sets up a correlation between two metrics of value.

   For this example, change the **[!UICONTROL Visits]** metric in the column to **[!UICONTROL Internal Searches]**. Right-click and select [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Add more metrics to the Correlation Matrix.

   Right-click in a metric column or row. For example, from the Metric menu, add

[!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   The new metric will appear in a column with a correlation number. You can add other metrics, such as **[!UICONTROL Email Signups]**, to build out the table.

   ![](assets/correlation_matrix_6.png)

   Or add metrics to rows to compare against metrics in columns.

   ![](assets/correlation_matrix_add_metric.png)

1. (optional) Constrain a metric by adding a dimension element.

   Right-click in the workspace and select **[!UICONTROL Table]**. From the open dimension table, press Ctrl + Alt and drag the element over a metric in a column or row. The element will appear next to the metric in brackets.

   For example, for the **[!UICONTROL Visits]** metric, you can constrain it by selecting the **[!UICONTROL Country]** as **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Notice that when you select a dimension element, the correlation changes in all metrics based on the selected dimension element. Only the Visit metric will be constrained for "New Zealand" once the dimension window is closed.

   >[!NOTE]
   >
   >If changing a metric with a dimension constraint (by right-clicking and selecting **[!UICONTROL Change Metric]**), the dimension element constraining the metric will be lost. You will need to add the dimension element again.

1. Create a [Binary Filter](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) to further constrain the metric. Right-click the metric in the table and select Binary Filter from the menu.

## Correlation Planning and Analysis Goals {#section-cc322da60b7e417ba29e72b0afeb6f79}

The following are general goals for building a Correlation Matrix.

**Identify the relationship between two metrics against a specified dimension**. In the example, the matrix was built around the core dimension, Day of the Week, with the metrics Visit, Email Signups, and SignIn Errors compared against Internal Searches, Login, and Survey Displayed metric events.

**Develop hypotheses to focus analysis**. After running a correlation analysis, your next step is to look for dependencies and correlation of the metrics. For example, understanding that internal searches has an effect on email sign-ups provides a path to predict that relationship and to modify marketing campaigns or web site navigation design.

**Identify metrics to include more advanced data mining algorithms**. In most cases, the key metrics will be identified because they will be seen affecting multiple correlations. You can now take those key metrics and apply them to additional data mining analysis for deeper insight.

## Correlation Matrix Feature Notes {#section-ef3626c665ea468a9ecdad624b4132f5}

**Filtering and selecting on dimension elements within a table compares like values**. For example, using Day of the Week dimension and then clicking into an element of that core dimension, such as clicking on a specific day within the Day of Week dimension table, renders a one to one match at 100% that provides no usable correlation. Because the root dimension was Day of the Week, any selection within the Day of the Week dimension table will alter the matrix to be a one-to-one correlation.

![](assets/correlation_matrix_10.png)

However, the 1 to 1 correlation (when a single selection is made of all elements) is only on that specific day. If you make multiple selections then it does not necessarily remain a 1 to 1 correlation, and will not always yield a 100 percent match regardless of selecting 1 or 1+ days of the week.

**Statistical correlations are not equal to the Correlated Data Model**, the historical reference of Adobe Analytics products. The statistical correlation in data workbench is based on the [Pearson Correlation model](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**Display Correlation in a Scatter Plot**. Right click the title on a Scatter Plot and choose [!DNL Display Correlation] from the [!DNL Visualization] menu. The Correlation value will display in the upper right section of the Scatter Plot.

>[!NOTE]
>
>The Scatter Plot and Pearsons matrix will display "Calculation Error" if the application is unable to run the Pearsons correlation calculation. This is usually due to insufficient data, which can cause the equation to attempt to divide by 0.

