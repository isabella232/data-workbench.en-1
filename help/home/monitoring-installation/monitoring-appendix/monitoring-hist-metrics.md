---
description: The following lists the metrics included in the data workbench Historical Monitoring Profile and how they are derived.
title: Metrics in the Data Workbench Historical Monitoring profile
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
---
# Metrics in the Data Workbench Historical Monitoring profile{#metrics-in-the-data-workbench-historical-monitoring-profile}

The following lists the metrics included in the data workbench Historical Monitoring Profile and how they are derived.

|  **Alert Criticals** | The sum of the Alert Critical dimension for each Ping.  |
|---|---|
|  **Alert Downs** | The sum of the Alert Down dimension for each Ping.  |
|  **Alert Warnings** | The sum of the Alert Warning dimension for each Ping.  |
|  **All Components** | The count of Pings where Component Check Success equals "1" divided by the Pings metric multiplied by 100.  |
|  **As Of Delay Minutes** | This metric is the sum of the As Of Delay Minutes for each Ping, then divided by the Pings metric.  |
|  **Blocks** | The sum of one for each Block.  |
|  **Block All** | All Blocks.  |
|  **Capacity Overall** | The Capacity Size Metric times 2 plus the Capacity Row metric, divided by 3.  |
|  **Capacity Row** | The sum of the Capacity Row Percentage dimension for each Ping divided by the Pings metric.  |
|  **Capacity Size** | The sum of the Capacity Size Percentage dimension for each Ping, divided by the Pings metric.  |
|  **Communications** | The number of Pings where Quick Check Success matches "1", divided by the Pings metric.  |
|  **Detailed Check Seconds** | The sum of the Detailed Check Seconds dimension for each Ping where the ping type is "server", divided by the Pings metric.  |
|  **Dimension GigaBytes** | The sum of Dimension Gigabytes for each Ping, divided by the Pings metric.  |
|  **Disk "x"** | The Disk metrics are calculated by taking the sum of their Disk Used Percentage for each Ping, divided by the Pings metric.  |
|  **Estimated Sweep Minutes** | This is the sum of the Estimated Sweep Dekaseconds for each Ping, divided by the Pings metric where Estimated Sweep Dekaseconds is greater than zero, all divided by 6.  |
|  **Fast Input MB per Minute** | The sum of Fast Input MegaBytes per Minute for each Ping divided by the number of Pings when Fast Input MegaBytes per Minute is greater than zero.  |
|  **Fast Input Mode** | Pings where Processing Mode dimension is equal to "Fast input" divided by Pings.  |
|  **Fast Merge MegaBytes per Minute** | The sum of Fast Merge Megabytes per Minute for each Ping, divided by Pings metric.  |
|  **Fast Merge Mode** | Pings where Processing Mode equals "fast merge" divided by the Pings metric.  |
|  **Field GigaBytes** | The sum of Field Gigabytes dimension for each Ping divided by Pings metric.  |
|  **Load** | The sum of the Load Average dimension for each Ping, divided by the Pings metric.  |
|  **Log Reading** | The sum of Log Reading Processing dimension for each Ping, divided by the Pings metric, all divided by 10.  |
|  **Memory Page** | The sum of Memory Page File Percentage for each Ping, divided by the Pings metric.  |
|  **Memory Physical** | The sum of the Memory Physical Percentage dimension for each Ping, divided by the Pings metric.  |
|  **Memory Query** | The sum of the Memory Query Percentage for each Ping, divided by the Pings metric.  |
|  **Memory Total GB** | The sum of Memory Physical MegaBytes Total dimension for each Ping, divided by the Pings metric.  |
|  **Network Connections** | This is the sum of the Network Connections for each Ping divided by the Pings metric.  |
|  **Pings x Capacity Overall** | The Pings metric multiplied by the Capacity Overall metric.  |
|  **Poll Latency Milliseconds** | The sum of the Poll Latency Centiseconds dimension for each Ping, divided by the Pings metric, all multiplied by 10.  |
|  **Query Running** | The sum of one for each Ping where Estimated Sweep Dekaseconds is greater than "0", divided by the Pings metric where Ping Type equals "server".  |
|  **Quick Check Seconds** | The sum of Quick Check Seconds for each Ping where Ping Type is equal to "server", divided by the Pings metric.  |
|  **Output Rows** | The sum of Output Rows dimension for each ping divided by the Pings metric, multiplied by 100000.  |
|  **Real Time Mode** | The number of Pings where Processing Mode dimension equals "real time", divided by the Pings metric, all multiplied by 100.  |
|  **Reprocessing Mode** | 100 minus the number of Pings where Processing Mode equals "real time" divided by the Pings metric, multiplied by 100.  |
|  **Stalled** |The sum of the Processing Stalled dimension in the Insight [Profile Status](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) profile.  |
|  **Temp DB** | The sum of Temp DB Space Percentage for each Ping, divided by the Pings metric.  |
|  **Transformation** | The sum of Transformation Percentage for each Ping divided by the Pings metric all divided by 10.  |
