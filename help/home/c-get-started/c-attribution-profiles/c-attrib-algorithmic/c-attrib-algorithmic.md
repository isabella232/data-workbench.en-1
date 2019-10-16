---
description: Best Fit Attribution is a machine-learning approach to assigning attribution values across the different channels of a successful conversion event. Data Workbench automatically evaluates contributions to success across a window of time per channel, and then builds an attribution model based on your customers' actual interaction patterns.
seo-description: Best Fit Attribution is a machine-learning approach to assigning attribution values across the different channels of a successful conversion event. Data Workbench automatically evaluates contributions to success across a window of time per channel, and then builds an attribution model based on your customers' actual interaction patterns.
seo-title: Best Fit Attribution
title: Best Fit Attribution
uuid: 0c51beb3-8f74-4f8e-9722-0c885140c8ce
---

# Best Fit Attribution{#best-fit-attribution}

Best Fit Attribution is a machine-learning approach to assigning attribution values across the different channels of a successful conversion event. Data Workbench automatically evaluates contributions to success across a window of time per channel, and then builds an attribution model based on your customers' actual interaction patterns.

**[!UICONTROL Best Fit Attribution]** lets you compare the interactions, or touches, that contributed to a successful sale, email sign-up, or other performance indicators. The attribution analysis automatically assigns weight to the most important touches and provides an attribution model per channel based on your data and responsive to your market and internal protocols.

![](assets/attrib_windows_5.png)

For example, if a customer visits your site through an organic search, then engages with a campaign, and then signs up for an email, [rules-based Attribution](/help/home/c-get-started/c-attribution-profiles/c-rules-attrib/c-rules-attrib.md) would identify the first touch or last touch, or evenly distribute success attribution across all touch points using preset attribution models. Where rules-based attribution is defined by the user, the Best Fit attributes sets values through an algorithm by calculating the probability of a conversion as a function of the observed touch points.

>[!NOTE]
>
>To run **Best Fit Attribution** in Data Workbench, you need to update your server certificate ( [!DNL .pem file]) to support Adobe Analytics Premium. You also need to add **Premium** to your custom [!DNL Profile.cfg] for the client and receive new certificates from Adobe ClientCare for Server and Report Server. 

## Basic Setup {#section-db597eaee462412ea7280d1426366c61}

See [Build a Best Fit Attribution](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-building.md#concept-fede6fc4f592475fa8b351b1765a522d) for step-by-step instructions.

**Set the Success metric** 
Define a metric representing a success event.

![](assets/attrib_windows_1.png)

The Success Metric is often *Orders*, although you can leverage Data Workbench to define a very complicated success metric in conjunction with the Success Window.

**Set the Touch metric** (optional)

Identify interactions to track that led to a successful conversion, then set the Touch metric over which attribution will be calculated.

>[!NOTE]
>
>Setting a Touch metric is only required if you are using it to derive Channel Metrics from drag and drop Dimension elements instead of using existing Channel metrics.

If you do not have a metric defined for campaigns or channels, but do have dimensions representing channels, the Best Fit Attribution can build them for you automatically based on the Touch metric.

For example, with the Touch Metric set as *Hits*, and given a dimension called *Media Type* with elements that include *Email*, *Press Release*, *Print Ad*, and *Social Media*, the visualization will generate Channel metrics of the form [!DNL Hits where Media Type = Email] when you drag and drop the element(s) onto the visualization. 

![](assets/attrib_windows_2.png)

The Touch metric then determines the allocation of attribution scores to identify marketing interactions considered influential for success, allowing you to qualify marketing touches for the population identified in the Success window. You can set metric such as *Page Views* or *Hits*, or use customized touch metrics specific to your needs.

In many cases, the Touch window should include the Success window to evaluate a long lead time in the sales cycle.

**Set the Revenue metric.**

You can opt to identify revenue across touch points by setting an appropriate revenue metric. If specified, the model will display the distribution of revenue over the input channels. ![](assets/attrib_windows_6.png)

You can set a revenue metric with currency data types to allocate success across all top touch points defined and analyzed. This metric breaks down the final sales revenue and allocates based on the weighting allocated by the algorithm.

**Set the Success and Touch Windows.**

The Success window defines the population to examine and the period for successful events, allowing you to indicate the windows of time and breadth of population to consider for the analysis through a workspace selection. The **Success** window defines the period and population to examine for success events. The **Touch** window specifies the historical time period to examine for channel interactions leading up to the success events.

>[!NOTE]
>
>Setting a Touch Metric is only required if you are trying to build Success metrics automatically by dragging dimension elements onto the visualization.

You can set a day, month, year, or any available time frame to constrain your evaluation of success and touch events across the sales cycle or for specific audiences entering your site. Creating windows to limit attribution allows you to focus your analysis on the relevant periods of time for your specific needs. 

![](assets/attrib_windows_4.png)

In many cases, you will want the Touch window to include the Success window to let you extend your analysis over a long lead time based on your sales window. Or you can track and analyze touches separate from the success event.

**Select the Channels.**

When entering channels you have two choices.

**Add the Touch Metric and add Dimension Elements to the Channels**

In many cases, you will want to break down the top touch points by dimension elements to define specific channels. Based on the element values, Best Fit Attribution will automatically select the top performers and rank them according to percentage and display them in a chart visualization.

![](assets/attrib_windows_7.png)

An attribution model will be built by drawing on the visitors who interacted during your Success window and examining the channel Touches during the Touch window that did or did not result in a successful event.

## Breaking Down by Channels {#section-a30592b84bc84f57bd2b988824e852d4}

When entering channels you have two options:

* Add a **Touch Metric** and then add **Dimension Elements** for the Channels.

  **or** 

* Create metrics that filter for the channel elements that you want to evaluate.

**Option 1: Add a Touch Metric and add Dimension Elements for Channels**.

This is the easier approach. Best Fit Attribution creates the metrics automatically to evaluate for attribution. In the example below the Touch Metric is ***Hits*** and Channels are: ***Display Campaigns***, ***Email Campaigns***, and ***SEM Campaigns***.

Using this method, Best Fit Attribution creates a metric in the background for evaluating the attribution across the channels (but you never see the auto-generated metric and they are not saved). In the example below, three metrics are created where Hits is filtered for each of the three channels (e.g, *Display Campaigns*, *Email Campaigns*, and *SEM Campaigns*). This is the easiest because you let the Best Fit Attribution create the metrics for you.

![](assets/attrib_touch_add_dims.png)

**Option 2: Create a Metric**.

In the second option, you create and save the metrics for the channels that you want to evaluate by filtering a specific channel. An example of a such a metric is shown below.

![](assets/attrib_create_metric.png)

Then, instead of entering a Touch Metric and Dimension Elements for the Channels you can click on the menu bar in the visualization and select **Inputs** > **Add Channel** and then select the metrics that you created. 

![](assets/attrib_results_2.png)

See the example of the second method below. You can see that the results of both options are identical. 
