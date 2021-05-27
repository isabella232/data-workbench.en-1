---
description: The following dimensions are available for use in the data workbench Server Status profile.
title: Dimensions in the Data Workbench Server Status profile
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
---
# Dimensions in the Data Workbench Server Status profile{#dimensions-in-the-data-workbench-server-status-profile}

The following dimensions are available for use in the data workbench Server Status profile.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Built from the x-trackingid field, this countable dimension represents the Servers currently running data workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Agent Version</b> </td> 
   <td colname="col2"> The cs-uri-query(af) value is used for this Simple Dimension. It is the Last Nonblank value for a Server. This displays the build date and time for the version(s) of the monitoring agent running. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Any Profile Reprocessing</b> </td> 
   <td colname="col2"> The cs-uri-query(aa) field is used for this Numeric Dimension, it is the value of the Last Row for a given Server, conditional on cs-uri-query(k) is not empty. This dimension is used to indicate if any profiles are Reprocessing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacity Row Percentage</b> </td> 
   <td colname="col2"> The cs-uri-query(r) field is used for this Numeric Dimension, it is the value of the Last Row for a given Server, conditional on cs-uri-query(k) is not empty. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacity Size Percentage</b> </td> 
   <td colname="col2"> The cs-uri-query(n) field is used for this Numeric Dimension, it is the value of the Last Row for a given Server, conditional on cs-uri-query(k) is not empty. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Common Name</b> </td> 
   <td colname="col2"> The sc-ur-query(am) field is used for this Simple Dimension, it is the value of the Last Nonblank value for a given Server. It displays the Common Name of the servers being monitored. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Component Check Success</b> </td> 
   <td colname="col2"> The cs-uri-query(v) field is used for this Simple Dimension, it is the value of the Last Row for a given Server. This dimension checks on the components of the server to verify they are properly functioning. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Components in Error</b> </td> 
   <td colname="col2"> A Crossrows transformation takes the Last Row value of the cs-uri-query(ao) and copies it into the x-components-in-error field. This Many to Many dimension displays any components in error on servers being monitored. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environment</b> </td> 
   <td colname="col2">The cs-uri-query(c) value is used for the Environment ID. The Last Row for a Block is used as the value for the dimension. This Simple Dimension will display the Environment in which your Servers are running (provided it is configured properly). <p><p>Note:  This dimension is set in insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimated Sweep Dekaseconds</b> </td> 
   <td colname="col2"> The x-estimated-sweep-dekaseconds field is used in this Numeric Dimension. This is the estimated sweep time of the servers divided by ten (reduced resolution of sweep measurement to make dimension more reasonably sized). <p><p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> The cs-uri-query(b) value is used for this dimension. The Simple dimension's value is the Last Row for a Block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping</b> </td> 
   <td colname="col2"> x-last-ping is x-unixtime divide by 10 (to accommodate Numeric dimensions size constraints). Last Ping is the Last Row for a given Block, and it represents the last time the monitoring agent logged the system health. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load Average</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(i) value. It is conditioned on cs-uri-query(k) not being empty. This dimension is used to calculate the average load on the servers in the system being monitored. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Page File Percentage</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(o) value. It is conditioned on cs-uri-query(k) not being empty. This dimension is used to calculate the percent of page file memory usage. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Physical MegaBytes Total</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(ag) value. It is conditioned on cs-uri-query(k) not being empty. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Physical Percentage</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(ag) value. It is conditioned on cs-uri-query(k) not being empty. This dimension is used to calculate the percent of physical memory usage of each Server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Query Percentage</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(s) value. It is conditioned on cs-uri-query(k) not being empty. This dimension is used to calculate the percent of query memory usage of each Server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Network Connections</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(q) value. It is conditioned on cs-uri-query(k) not being empty. This is used to show the number of network connections there are for a given server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Poll Latency Centiseconds</b> </td> 
   <td colname="col2"> This dimension is used to calculate the poll latency. The cs-uri-query(m) value is divided by 10 to reduce dimension size, and copied into the x-poll-latency-centiseconds field. This is a Numeric dimension which takes the Last Row for a given server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quick Check Success</b> </td> 
   <td colname="col2"> This is a Simple dimension built from the cs-uri-query(g) value of the Last Row for a given Server. It is used to calculate the quick check metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB Space Percentage</b> </td> 
   <td colname="col2"> The last row of the cs-uri-query(an) value is copied into the x-temp-db-space-percentage field. This is a Numeric Dimension that is used to calculate the percentage of used Temp DB space on a given server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight Version</b> </td> 
   <td colname="col2"> The cs-uri-query(ab) value is used for this Simple Dimension. It is the Last Nonblank value for a Server. This displays the version(s) of data workbench server running on each server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Group</b> </td> 
   <td colname="col2"> Grouping word that gives you another way to filter the resulting dataset. <p>Note:  This dimension is set in insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metrics</b> </td> 
   <td colname="col2"> The following lists the metrics included in the data workbench Profile Monitoring Profile and how they are derived. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacity Overall</b> </td> 
   <td colname="col2"> This is the Capacity Size metric times two plus the Capacity Row metric divided by 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacity Row</b> </td> 
   <td colname="col2"> This is the sum of the Capacity Row Percentage for each Server divided by Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacity Size</b> </td> 
   <td colname="col2"> This is the sum of the Capacity Size Percentage for each Server divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Component Check</b> </td> 
   <td colname="col2"> This is the number of Servers where Component Check Success equals one, divided by the Server where Service is DPU or FSU, all multiplied by 100 (to make it a percentage). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disk "x"</b> </td> 
   <td colname="col2"> The Disk metrics are calculated by taking the sum of their Disk Used Percentage for each Server, divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimated Sweep Minutes</b> </td> 
   <td colname="col2"> This is the sum of the Estimated Sweep Dekaseconds for each Server, divided by the Servers metric where Estimated Sweep Dekaseconds is greater than zero, all divided by 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Time</b> </td> 
   <td colname="col2"> The sum of Last Ping for each Block divided by Blocks, then multiplied by 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> This is the sum of the Load Average for each Server, divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Page File</b> </td> 
   <td colname="col2"> This is the sum of the Memory Page File Percentage for each Server, divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Physical</b> </td> 
   <td colname="col2"> This is the sum of the Memory Physical Percentage for each Server, divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memory Query</b> </td> 
   <td colname="col2"> This is the sum of the Memory Query Percentage for each Server, divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Network Connections</b> </td> 
   <td colname="col2"> This is the sum of the Network Connections for each Server divided by the Servers metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Poll Latency Milliseconds</b> </td> 
   <td colname="col2"> This is the sum of the Poll Latency Centiseconds for each Server, divided by the Servers metric, all of which is multiplied by 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quick Check</b> </td> 
   <td colname="col2"> This is the number of Servers where Quick Check Success equals one, divided by the Servers metric, all of which is multiplied by 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Servers</b> </td> 
   <td colname="col2"> This is the sum of one for each Server, or the total number of monitored Servers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB</b> </td> 
   <td colname="col2"> This is the sum of the Temp DB Space Percentage for each Server, divided by the Servers metric. </td> 
  </tr> 
 </tbody> 
</table>
