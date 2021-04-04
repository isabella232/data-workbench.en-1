---
description: Data workbench includes built-in metrics.
solution: Analytics
title: Built-in Metrics
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
---
# Built-in Metrics{#built-in-metrics}

Data workbench includes built-in metrics.

The following table lists the available built-in metrics for data workbench: 

|  Built-in Metric  | Description  |
|---|---|
|  As Of  | The As Of time of the dataset in 100 nanoseconds intervals since January 1, 1600 00:00 UTC. The As Of timestamp is the latest time in the dataset for which all data has definitely been processed.  |
|  Log Bytes Read  | The total amount of compressed data (in bytes) that has so far been processed during the log processing phase.  |
|  Log Bytes Total  | The total amount of compressed data (in bytes) in log files matching the configured log sources criteria and start and end date range of the dataset. If log processing is paused in the Log Processing Mode configuration file then Log Bytes Total will be the same as Log Bytes Read.  |
|  Log Processing Progress  | The percentage completion of the log processing phase of Insight Server data processing.  |
|  Total Decoded Log Entries  | The number of entries in the log files that were successfully decoded as a part of the log processing phase of Insight Server data processing.  |
|  Total Filtered Log Entries  | The number of entries in the log files that after being decoded were accepted by the robot filter and the log entry conditions and other filters that are applied as a part of the log processing phase of Insight Server data processing.  |
|  Total Log Entries  | The number of entries in the log files that have so far been processed by the log processing phase of Insight Server data processing.  |
|  Total Processed Log Entries  | The number of filtered log entries that have been incorporated into the Adobe dataset.  |
|  Transformation Progress  | The percentage completion of the transformation phase of Insight Server data processing.  |
|  Uncompressed Log Bytes Read  | The total amount of uncompressed data (in bytes) that has so far been processed during the log processing phase.  |
