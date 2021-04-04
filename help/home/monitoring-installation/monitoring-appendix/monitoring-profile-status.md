---
description: The following dimensions are available for use in the data workbench Profile Status profile.
solution: Analytics
title: Dimensions in the Data Workbench Profile Status profile
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
---
# Dimensions in the Data Workbench Profile Status profile{#dimensions-in-the-data-workbench-profile-status-profile}

The following dimensions are available for use in the data workbench Profile Status profile.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2"> This is the only countable in this configuration and exists as the root for all dimensions. A block can be considered a server. It is using the x-trackingid field. The block ID is a hash of the server name plus host name, so there will be approximately one block per server per profile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>As of Delay Minutes</b> </td> 
   <td colname="col2"> cs-uri-query(bi) is placed into the x-as-of-delay-minutes field and rounded to the nearest minute. As of Delay Minutes is a numeric dimension that takes the Last Row from x-as-of-delay-minutes for a block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environment</b> </td> 
   <td colname="col2"> The cs-uri-query(c) value is used for the Environment ID. The Last Row for a Block is used as the value for the dimension. This Simple Dimension will display the Environment in which your Servers are running (provided it is configured properly). <p>This can be set in the insight_monitor_agent.cfg file </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MegaBytes per Minute</b> </td> 
   <td colname="col2"> The cs-uri-query(bj) value is used for this dimension. The Last Row for a block is used as the value for the dimension. If the dataset is in Fast Input this Numeric Dimension's value will display the MB per minute at which the system is inputting data. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MegaBytes per Minute</b> </td> 
   <td colname="col2">The cs-uri-query(bk) value is used for this dimension. The Last Row for a Block is used as the value for the dimension. If the dataset is in Fast Merge This Numeric Dimension's value will display the MB per minute at which the system is merging. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> The cs-uri-query(bg) value is used for this dimension. The value is divided by 1000 and rounded to the nearest whole number. This Numeric Dimension's value will display the amount of space the Fields in the dataset are using. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> The cs-uri-query(b) value is used for this dimension. The Simple dimension's value is the Last Row for a Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping</b> </td> 
   <td colname="col2">x-last-ping is x-unixtime divide by 10 (to accommodate Numeric dimensions size constraints). Last Ping is the Last Row for a given Block, and it represents the last time the monitoring agent logged the system health. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Log Reading Percentage</b> </td> 
   <td colname="col2">the cs-uri-query(be) value is used for this numeric dimension. It is the Last Row for a given Block. This dimension is used to calculate the percentage of logs being read. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Mode ID</b> </td> 
   <td colname="col2"> The cs-uri-query(bb) value is used for this Simple Dimension. It the Last Row for a given Block. Processing Mode ID allows one to see what mode of processing the system is in (Fast Input, Fast Merge, Real Time). <p>Note:  This dimension is hidden then re-exposed with friendly values in the client-side dimension Processing Mode. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Stalled</b> </td> 
   <td colname="col2"> The x-processing-stalled field is created through various conditions to indicate whether the profile is currently running or not. It is a simple dimension. <p>Note:  This dimension works best when there are a large number of input logs to fairly distribute amongst the DPUs. If there is, for example, only one large file loaded per day, then data workbench can appear to "stall" for an hour or more resulting in a false positive reading from this dimension. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profile</b> </td> 
   <td colname="col2"> The cs-uri-query(ba) value is used for this Simple Dimension. This dimension displays the name(s) of the profiles currently being monitored. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source Furthest Behind</b> </td> 
   <td colname="col2"> The last row of cs-uri-query(bl) is copied into the x-source-furthest-behind field. The Simple Dimension uses the Last Row for a given Block. This dimension displays the when the last contact with a data source occurred. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformation Percentage</b> </td> 
   <td colname="col2"> the cs-uri-query(bf) value is used for this numeric dimension. It is the Last Row for a given Block. This dimension is used to calculate the percentage of complete data transformation. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Time Dimensions</b> </td> 
   <td colname="col2"> Hour, Day, Week, Month, Hour of Day, and Day of Week are all derived from the x-timestamp field. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Group</b> </td> 
   <td colname="col2"> Grouping word that gives you another way to filter the resulting dataset. Set in the insight_monitor_agent.cfg file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metrics</b> </td> 
   <td colname="col2"> The following lists the metrics included in the data workbench Profile Monitoring Profile and how they are derived. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>As Of Delay Minutes</b> </td> 
   <td colname="col2"> This metric is the sum of the As Of Delay Minutes for each Block, then divided by the Blocks metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>As Of Delay Seconds</b> </td> 
   <td colname="col2"> This metric is the sum of the As Of Delay Seconds for each Block, and divided by the total number of Blocks. (As of Delay Seconds Dimension not configured out of the box) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocks</b> </td> 
   <td colname="col2"> Sum one for each Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MB per Minute</b> </td> 
   <td colname="col2"> The sum of Fast Input MegaBytes per Minute for each Block divided by the number of Blocks when Fast Input MegaBytes per Minute is greater than zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MB per Minute</b> </td> 
   <td colname="col2"> The sum of Fast Merge MegaBytes per Minute for each Block divided by the number of Blocks when Fast Merge MegaBytes per Minute is greater than zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> The sum of Field Gigabytes for each Block divided by Blocks metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Age</b> </td> 
   <td colname="col2"> The As Of Time minus Last Ping Time. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Time</b> </td> 
   <td colname="col2"> The sum of Last Ping for each Block divided by Blocks, then multiplied by 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Log Reading</b> </td> 
   <td colname="col2"> Where Log Reading Percentage is greater than zero, Log Reading is the sum of Log Reading Percentage for each Block, divided by Blocks metric, all of which is divided by 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Stalled</b> </td> 
   <td colname="col2"> The sum of the Processing Stalled Dimension for each Block, divided by the Blocks metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformation</b> </td> 
   <td colname="col2"> The sum of Transformation Percentage for each Block divided by the Blocks metric, when Transformation Percentage is greater than zero, all divided by 10. </td> 
  </tr> 
 </tbody> 
</table>
