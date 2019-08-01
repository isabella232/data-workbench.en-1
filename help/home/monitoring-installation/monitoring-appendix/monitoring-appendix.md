---
description: This document describes the profiles with their fields, dimensions, and metrics employed by the data workbench Monitoring Profile.
seo-description: This document describes the profiles with their fields, dimensions, and metrics employed by the data workbench Monitoring Profile.
seo-title: Data Workbench Profile Dimensions and Metrics
solution: Analytics
title: Data Workbench Profile Dimensions and Metrics
topic: Data workbench
uuid: 24017938-acf1-480f-9d5d-d0c45e56e2eb
index: y
internal: n
snippet: y
---

# Data Workbench Profile Dimensions and Metrics{#data-workbench-profile-dimensions-and-metrics}

This document describes the profiles with their fields, dimensions, and metrics employed by the data workbench Monitoring Profile.

 To monitor data workbench servers, data is collected using a script that parses the Detailed Status while also capturing specific server information. Data workbench server information is then passed to a page tag call for the data workbench Sensor to collect and save to a VSL file.

## Profiles Employed by the Data Workbench Monitoring Profile {#section-b5b1234f55c3407dae8e68b031b7cd7f}

These profiles provide dimensions and metrics that allow you to view server state and performance data:

* [Dimensions in the Insight Profile Status profile](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) 
* [Dimensions in the Insight Server Status profile](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a) 
* [Dimensions in the Insight Historic profile](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0) 
* [Metrics in the Insight Historical Monitoring profile](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

The Status profiles allow you to see how data workbench is currently performing from an operational perspective. The **Profile Status** profile and the **Server Status** profile gather data from the Detailed Status and the data workbench servers. All gathered data is placed into the `cs-uri-query` field for use.

The **Historic profiles** allow you to assess the impact of configuration and hardware changes using historical data. The historical profile may be the most useful because it allows you to assess the impact of configuration and hardware changes over time. 
