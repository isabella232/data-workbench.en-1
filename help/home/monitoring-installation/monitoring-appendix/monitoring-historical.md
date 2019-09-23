---
description: The following dimensions are available for use in the data workbench Historic profile.
seo-description: The following dimensions are available for use in the data workbench Historic profile.
seo-title: Dimensions in the Data Workbench Historic profile
solution: Analytics
title: Dimensions in the Data Workbench Historic profile
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
---

# Dimensions in the Data Workbench Historic profile{#dimensions-in-the-data-workbench-historic-profile}

The following dimensions are available for use in the data workbench Historic profile.

## Dimensions in the Data Workbench Historic profile {#section-96f1b64f5cb84411b630f97f227d888d}

The following dimensions are available for use in the data workbench Historic profile.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2">This is the only countable in this configuration, it is the root for all dimensions. A block can be considered a server. It is using the x-trackingid field. <p>Note:  The block ID is a hash of the server name plus host name, so there will be approximately one block per server per profile. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> This is a countable dimension built off of the Block countable. Each row of data in the profile is a ping from the monitoring agent. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Alert Critical</b> </td> 
   <td colname="col2"> Numeric Dimension built from the cs-uri-query(ad) value. It is built at the Ping level conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Alert Down</b> </td> 
   <td colname="col2"> Numeric Dimension built from cs-uri-query(ac) value. It is built at the Ping level, conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Alert Warning</b> </td> 
   <td colname="col2"> Numeric Dimension built from cs-uri-query(ae) value. It is built at the Ping level conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Any Profile Reprocessing</b> </td> 
   <td colname="col2"> Numeric Dimension built from cs-uri-query(aa) value. It is built at the Ping level conditioned that cs-uri-query(a) matches "1" and cs-uriquery(k) is not empty. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>As of Delay Minutes</b> </td> 
   <td colname="col2"> cs-uri-query(bi) is placed into the x-as-of-delay-minutes field and rounded to the nearest minute. It is built at the Ping level conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Capacity Row Percentage</b> </td> 
   <td colname="col2"> Numeric Dimension built from cs-uri-query(r) value. It is built at the Ping level conditioned that cs-uri-query(a) matches "1" and cs-uriquery(k) is not empty. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Capacity Size Percentage</b> </td> 
   <td colname="col2"> Numeric Dimension built from cs-uri-query(n) value. It is built at the Ping level conditioned that cs-uri-query(a) matches "1" and cs-uriquery(k) is not empty. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Component Check Success</b> </td> 
   <td colname="col2"> Simple Dimension built from cs-uri-query(v) value. It is built at the Ping level, and conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Components in Error</b> </td> 
   <td colname="col2"> cs-uri-query(ao) is split by the "|" delimiter and copied into the x-components-in-error field. Many to Many Dimension built from the x-components-in-error field. Built at the Ping level. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Detailed Check Seconds</b> </td> 
   <td colname="col2"> Numeric Dimension built from cs-uri-query(l) value. It is built at the Ping level conditioned that cs-uri-query(k) is not empty. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Detailed Check Success</b> </td> 
   <td colname="col2"> Simple Dimension built from the cs-uri-query(k) value. It is built at the Ping level conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) is copied into the x-dimension-gigabytes field. The x-dimension-gigabytes field is user for this Simple Dimension, conditioned on cs-uri-query(a) matching "2". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Disk "x" Used Percentage</b> </td> 
   <td colname="col2"> These Numeric Dimensions are configured from the cs-uri-query(ah, ai, aj, ak, al) values. They are built at the Ping level and conditioned on cs-uri-query(a) matches "1" and cs-uri-query(k) is not empty. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Estimated Sweep Dekaseconds</b> </td> 
   <td colname="col2"> The x-estimated-sweep-dekaseconds field is used in this Numeric Dimension. This is the estimated sweep time of the servers divided by ten (reduced resolution of sweep measurement to make dimension more reasonably sized). <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Fast Input MegaBytes per Minute</b> </td> 
   <td colname="col2"> The cs-uri-query(bj) value is used for this dimension. The Last Row for a block is used as the value for the dimension. If the dataset is in Fast Input this Numeric Dimension's value will display the MB per minute at which the system is inputting data. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Fast Merge MegaBytes per Minute</b> </td> 
   <td colname="col2">The cs-uri-query(bk) value is used for this dimension. The Last Row for a Block is used as the value for the dimension. If the dataset is in Fast Merge This Numeric Dimension's value will display the MB per minute at which the system is merging. <p><p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2">The cs-uri-query(bg) value is used for this dimension. The value is divided by 1000 and rounded to the nearest whole number. This Numeric Dimension's value will display the amount of space the Fields in the dataset are using. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Group</b> </td> 
   <td colname="col2"> Simple Dimension built at the Ping level from the cs-uri-query(x) value. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> The cs-uri-query(b) value is used for this dimension. The Simple dimension's value is the Last Row for a Block. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Last Ping</b> </td> 
   <td colname="col2"> the x-unixtime field is copied into x-last-ping and divided by 10 to reduce the cardinality. The Numeric Dimension is built at the Block level and uses the x-last-ping field. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Load Average</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the Last Row for a given Server's cs-uri-query(i) value. It is conditioned on cs-uri-query(k) not being empty. This dimension is used to calculate the average load on the servers in the system being monitored. <p><p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Log Reading Percentage</b> </td> 
   <td colname="col2">the cs-uri-query(be) value is used for this numeric dimension, built at the Ping level. This dimension is used to calculate the percentage of logs being read. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Memory Page File Percentage</b> </td> 
   <td colname="col2"> This is a Numeric dimension using cs-uri-query(o) value, built at the Ping level. It is conditioned on cs-uri-query(k) not being empty, and cs-uri-query(a) matching "1". This dimension is used to calculate the percent of page file memory usage. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Memory Physical MegaBytes Total</b> </td> 
   <td colname="col2">This is a Numeric dimension using the cs-uri-query(ag) value, built at the Ping level. It is conditioned on cs-uri-query(k) not being empty, and cs-uri-query(a) matching "1. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Memory Physical Percentage</b> </td> 
   <td colname="col2">This is a Numeric dimension using the cs-uri-query(ag) value, built at the Ping level. It is conditioned on cs-uri-query(k) not being empty, and cs-uri-query(a) matching "1. This dimension is used to calculate the percent of physical memory usage of each Server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Memory Query Percentage</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the cs-uri-query(s) value at the Ping level. It is conditioned on cs-uri-query(k) not being empty and cs-uri-query(a) matching "1. This dimension is used to calculate the percent of query memory usage of each Server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Network Connections</b> </td> 
   <td colname="col2"> This is a Numeric dimension using the cs-uri-query(q) value built at the Ping level. It is conditioned on cs-uri-query(k) not being empty and cs-uri-query(a) matching "1. This is used to show the number of network connections there are for a given server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Output Rows</b> </td> 
   <td colname="col2"> cs-uri-query(bh) value is divided by 100000 and copied into the x-output-rows field to reduce the size of the dimension. X-output-rows is used in a Numeric Dimension built at the Ping level, conditioned that cs-uri-query(a) matches "2". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Ping Type ID</b> </td> 
   <td colname="col2"> Simple Dimension built using the cs-uri-query(a) value at the Ping level. This shows what kind of Ping was recorded. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Poll Latency Centiseconds</b> </td> 
   <td colname="col2">The cs-uri-query(m) value is divided by 10 to reduce dimension size, and copied into the x-poll-latency-centiseconds field. This is a Numeric dimension built at the Ping level, conditioned that cs-uri-query(k) is not empty, and cs-uri-query(a) matches "1"/ This dimension is used to calculate the poll latency. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Processing Mode ID</b> </td> 
   <td colname="col2"> The cs-uri-query(bb) value is used for this Simple Dimension, built at the Ping level. It is conditioned that cs-uri-query(bb) is not empty, and that cs-uri-query(a) matches "2" Processing Mode ID allows one to see what mode of processing the system is in (Fast Input, Fast Merge, Real Time). <p>Note:  This dimension is hidden then re-exposed with friendly values in the client-side dimension Processing Mode. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Profile</b> </td> 
   <td colname="col2"> The cs-uri-query(ba) value is used for this Simple Dimension, it is built at the Ping level. This dimension displays the name(s) of the profile(s) currently being monitored. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Quick Check Seconds</b> </td> 
   <td colname="col2"> The cs-uri-query(h) value is used for this Numeric Dimension. It is built at the Ping level conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Quick Check Success</b> </td> 
   <td colname="col2"> This is a Simple dimension built from the cs-uri-query(g) value built at the Ping level. It is used to calculate the quick check metric. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Real Time Processing Percentage</b> </td> 
   <td colname="col2"> Numeric Dimension using the cs-uri-query(t) value built at the Ping level. It is conditioned that cs-uri-query(a) matches "1". </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Source Furthest Behind</b> </td> 
   <td colname="col2"> Simple Dimension built from the cs-uri-query(bl) value built at the Ping level. This dimension displays the when the last contact with a data source occurred. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Temp DB Space Percentage</b> </td> 
   <td colname="col2">Numeric Dimension built using the cs-uri-query(an) value, built at the Ping level. It is conditioned that cs-uri-query(k) is not empty, and cs-uri-query(a) matches "1". It is used to calculate the percentage of used Temp DB space on a given server. <p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Transformation Percentage</b> </td> 
   <td colname="col2">the cs-uri-query(bf) value is used for this numeric dimension. It is built at the Ping level. This dimension is used to calculate the percentage of complete data transformation. <p><p>Note:  This dimension is hidden because it is only useful when averaged into a metric. </p></p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Data Workbench Version</b> </td> 
   <td colname="col2"> The cs-uri-query(ab) value is used for this Simple Dimension. It is built at the Ping level and conditioned that cs-uri-query(ab) is not empty, and cs-uri-query(a) matches "1". This displays the version(s) of data workbench server running on each server. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Data Workbench Version Major</b> </td> 
   <td colname="col2"> The cs-uri-query(ab) value is split and the major release value is copied into the x-insight-version-major field. It is a Simple Dimension built at the Ping level and conditioned that x-insight-version-major is not empty, and cs-uri-query(a) matches "1". </td> 
  </tr> 
 </tbody> 
</table>

<a id="section_76D8A4B07BB947558EBED1123EA203D5"></a>

