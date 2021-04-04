---
description: Trend lines lets you overlay graphs to compare and interpret data.
title: Trend Lines
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
---
# Trend Lines{#trend-lines}

Trend lines lets you overlay graphs to compare and interpret data.

Like the [Scatter Plot](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) visualization, you can now set trend lines on a graph visualization to display the rate of change based on linear, exponential, power, or polynomial lines. The Trend Line feature allows you to overlay trend lines on a graph, most commonly over a Time dimension.

For example, in this graph comparison, we can see that Visits are trending up, but Orders are trending down.

![](assets/trend_line.png)

To add a Trend Line

1. Open a graph and right-click the metric name in the upper left corner. 
1. Click **[!UICONTROL Trend Lines]** and select from the options. 

   ![](assets/trend_line_graph.png)

   You can select the trend line to appear over the graph as **Simple Linear**, **Exponential**, **Power**, or **Polynomial**. Polynomial will create a polynomial regression trend line. Simple Linear will create a trend line as the rate of change along the regression line. Exponential calculates a trend line as y = b&#42;exp( a&#42;x ) and Power as y = b&#42;x`<sup>a</sup>`.

   The trend will be calculated and rendered on the graph, and a callout will open displaying detailed information of the trend equation.

   ![](assets/trend_line_detail.png)
