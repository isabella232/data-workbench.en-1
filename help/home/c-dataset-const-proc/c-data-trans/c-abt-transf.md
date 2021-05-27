---
description: Transformations enable you to extract information available in your data files and manipulate it into a more useful form.
title: About Transformations
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
---
# About Transformations{#about-transformations}

Transformations enable you to extract information available in your data files and manipulate it into a more useful form.

Transformations operate on the log entries (you can think of log entries as rows of data) in your log sources. For each row of data, the transformation takes the value of the specified input field, performs a set of processing steps, and records the result in the output field that you specify. You can define transformations to be executed during either the log processing or transformation phase of the dataset construction process:

* **During log processing:** Transformations executed during the log processing phase of dataset construction are applied to each event data record (log entry) to update existing log fields or produce new fields. The results of the transformations are used along with log entry conditions to evaluate which log entries are filtered out of the dataset during log processing. 
* **During transformation:** Transformations executed during the transformation phase of dataset construction operate on the fields of data passed from log processing to create extended dimensions that you can use in your analyses. See [Extended Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>The data input to transformation from log processing is ordered by time and grouped by the tracking ID in your source data. Several transformations require that the data is in this form and work only when defined in during transformation.

Changes to transformations must be made with care. Transformations do not affect which log entries flow into the dataset construction process, but they do affect the results presented. This permits changes to be made in what is being analyzed without changing the data upon which the analysis is based. However, changes in transformations can fundamentally alter the values produced in analyses.
