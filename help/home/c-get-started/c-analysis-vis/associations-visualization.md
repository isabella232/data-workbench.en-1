---
description: The Association Table visualization let you associate metrics with metrics, dimensions, and dimension elements using Cramer's V algorithm.
title: Association Table visualization
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
---
# Association Table visualization{#association-table-visualization}

The Association Table visualization let you associate metrics with metrics, dimensions, and dimension elements using Cramer's V algorithm.

The Association Table compares values with Cramer's V calculation rather than using Pearson's correlation coefficient as used in the [Correlation Matrix](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) and [Correlation Chord](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) visualizations (these can only compare metrics, while the Association Table and [Association Chord](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) can compare metrics, dimensions, and elements).

## Build an Association Table {#section-87ed12ccc1af4196a1b6534e621c4cbb}

The Association Table compares metrics over a countable or non-countable dimension. The table can be modified to highlight associations within the visualization through color picking or to render it as a text map, heat map, or both.

1. Open an Association Table.

   Right-click [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Select an extended dimension—a Clickthrough, Hit, Product, Visit, or Visitor dimension. An Association Table will open with the extended dimension identified in the corner and its associated metric placed in both the row and column.

   ![](assets/association_table1.png)

   The Associations Table uses Cramer's V as a symmetrical correlation, resulting in selected metrics, dimensions, and elements values reflected in both the columns and rows of an Association Table. For example, selecting the **Product** extended dimension uses the **[!UICONTROL Visits]** metric as the associated metric in both the row and column of the table, resulting in a perfect yet useless comparison (1.00) because the compared values are identical. 

1. Add more values to the Association Table.

   Right-click in a column or row and select **Add Metric** or **Add Dimension**. You can also drag metrics and dimensions from a **Finder** panel. Dimension elements can also be dragged and dropped from an open table to the table visualization.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >There is a limit of ten rows and columns allowed in the Association Table.
