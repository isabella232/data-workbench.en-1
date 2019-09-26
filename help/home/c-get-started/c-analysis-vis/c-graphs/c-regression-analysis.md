---
description: The Bar Graph in Data Workbench now includes a regression comparison for multiple metrics across multiple graphs.
seo-description: The Bar Graph in Data Workbench now includes a regression comparison for multiple metrics across multiple graphs.
seo-title: Regression Analysis Graph
title: Regression Analysis Graph
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
---

# Regression Analysis Graph{#regression-analysis-graph}

The Bar Graph in Data Workbench now includes a regression comparison for multiple metrics across multiple graphs.

[Bar graphs](https://marketing.adobe.com/resources/help/en_US/insight/client/c_graphs.html) in Data Workbench let you regress metrics in one graph to metrics in another graph. If you have multiple graphs, you can compare a metric (as the independent variable) to a graph evaluating other metrics (as dependent variables). This lets you determine the strength of the relationship between one dependent variable (the metric established first) and a series of other changing metrics (regressions with the established dependent metric).

The regression analysis on a graph visualization allows analysts to perform "what-if" scenarios. For example, if visits increase to this level, what impact will this increase have on revenue?

**Setting up Regression Analysis**

1. Select graph as a dependent metric for a regression comparison.

   Right-click on the graph and select **Set as base metric for regression**.

   ![](assets/c_graph_regression_1.png)

1. Set other metric graphs as independent variables.

   Right-click metric and select **[!UICONTROL Regress with `<base metric name>`]** for other metrics.

   ![](assets/c_graph_regression.png)

1. View regression by right-clicking on the graph to move the bar up and down.

   If you right-click on the graph for a specific value, you can then see the regression ratios for each metric based for upward or downward values.

   ![](assets/c_graph_regression_2.png)

   For example, if my Page Views decrease to 86,041, then the other metrics will have these values: Visits at 12,183 and Visitors by Visit at 12,028.

   ![](assets/c_graph_regression_3.png)

   If Visitors by Visits values increase to 26,141, then the other metrics will be Visits at 26,560 and Page Views will be at 189,091.

