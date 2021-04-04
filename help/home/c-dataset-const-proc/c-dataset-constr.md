---
description: An Adobe dataset contains the data that has been loaded and processed by the data workbench server.
solution: Analytics
title: Understanding Dataset Construction
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
---
# Understanding Dataset Construction{#understanding-dataset-construction}

An Adobe dataset contains the data that has been loaded and processed by the data workbench server.

 The steps involved in the loading and processing of the data by the data workbench server (InsightServer64.exe) make up the dataset construction process.

>[!NOTE]
>
>A data workbench server that processes and serves data from an Adobe dataset is called a data processing unit or DPU. It is sometimes referred to as a processing server or a query server. Data workbench and [!DNL Report] clients interact with DPUs directly.

During dataset construction, the data workbench server reads source data from log sources, applies transformations to specific fields of data, and defines extended dimensions to be created from the transformed fields. The construction process occurs in two phases: *Log Processing* and *Transformation*. After the dataset is constructed, you can use the dataset's extended dimensions to create derived metrics and dimensions for your specific analysis purposes.

Dataset construction is like a manufacturing process. You select the data (the raw materials) to be used to build the dataset, and you define the data transformations (the process steps) that manipulate the information available in the data to create extended dimensions (the manufactured products).

<!--
c_log_proc.xml
-->

The logs are filtered, and the fields of data that are to be passed to the transformation phase are identified. At the end of the log processing phase, the data is grouped by tracking ID (that is, all log entries with the same tracking ID are grouped together) and ordered in time. During the log processing phase, you cannot access the processed data to use for analysis.

## Specifying Log Sources {#section-75279dd6a7304d469735562796741d0f}

Log sources are files that contain the data to be used to build a dataset. The data available in the log sources is called event data because each data record represents a transaction record or a single instance of an event. In addition, each record, or log entry, contains a value referred to as a tracking ID.

>[!NOTE]
>
>When selecting log sources, make sure that each log entry contains a tracking ID for the entity that is to represent the highest level at which your data is to be grouped. For example, if you are working with data collected from website traffic, you are likely to choose visitor to be this entity. Each visitor has a unique tracking ID, and all of the data about a particular site visitor can be grouped together. For assistance, contact Adobe.

A log sources event data is collected in real-time by [!DNL Sensors] or extracted from archived data sources by Insight Server. Event data collected by Sensors from HTTP and application servers is transmitted to Insight Servers, which convert the data into highly compressed log ( [!DNL .vsl]) files. Event data that resides in a flat file, XML file, or an ODBC data source is read by Insight Server, which provides decoders that you define to extract a common set of log fields from these different formats.

## Defining Transformations {#section-55a8cdb47379484081e53087f074778d}

A transformation is a set of instructions that you can define to extract or manipulate information in the event data. Each transformation that you define is applied to each event data record (log entry) to update existing log fields or produce new fields. The results of transformations are used along with log entry conditions to evaluate which log entries are filtered out of the dataset during log processing.

Not all types of transformations can be used during the log processing phase of the dataset construction process.

## Filtering Logs {#section-6172ca0fb0eb4177925151bb49fdbc02}

The dataset contains several parameters used to filter the data flowing out of the transformations. Filtering is used to specify which log entries are used in subsequent processing steps. For example, filters can be defined by, time range, the status of the server's response, or IP address and user-agent information. The [!DNL Log Entry Condition] is a customizable filtering test. The test looks for certain conditions in the fields of each log entry to determine whether that entry should proceed further in the dataset construction process. If a log entry does not meet the condition, the entry is removed from the construction process.

## Identifying Fields for Transformation {#section-eef98ca723e54547b887aefdf0514c47}

If a field of data is to be passed from the log processing phase to the transformation phase for further processing, you must identify it during log processing. This requirement applies regardless of whether the field is available from the log sources or created from data transformations applied to the data during log processing.

<!--
c_transformation.xml
-->

During the transformation phase of dataset construction, processing occurs on the grouped and ordered data that is output from log processing. Additional data transformations are performed and extended data dimensions are created for use in your analyses. During the transformation phase, you can access a statistical sample of the data that gets larger as the transformation phase nears completion.

## Defining Transformations {#section-001b3fd4c1dd4dd38a5536872bc9de68}

You can define transformations to be used during the transformation phase of the dataset construction process to facilitate the creation of the extended dimensions. Each transformation is applied to each event data record (log entry) passed from log processing.

## Filtering Logs {#section-3fed0a00ca344a719b5e8db363f64f06}

The [!DNL Log Entry Condition] can be applied during transformation to look for specific conditions in the fields of each log entry coming from log processing. If a log entry does not meet the condition, the entry is removed from the construction process.

## Defining Extended Dimensions {#section-25efafd0bfc84c86b9717d453a88c91b}

Extended dimensions are the final products of the dataset construction process. They represent relationships between the log fields in the data. You use them to create visualizations, build extended metrics, or perform analysis to understand the operations and issues specific to your business.
