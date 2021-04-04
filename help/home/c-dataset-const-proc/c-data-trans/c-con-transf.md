---
description: Table showing what conventions apply when constructing transformations.
solution: Analytics
title: Conventions for Constructing Transformations
topic: Data workbench
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
---
# Conventions for Constructing Transformations{#conventions-for-constructing-transformations}

Table showing what conventions apply when constructing transformations.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Convention </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sequential execution </td> 
   <td colname="col2"> <p>The transformations within a dataset configuration file are applied to the log entries sequentially (that is, in the order in which they are listed in the configuration file). Therefore, transformations must be listed in the order their outputs are used as inputs to other transformations. More specifically, if the output of one transformation is used as the input to another transformation, it is important for that former transformation to be listed prior to the latter transformation in the dataset configuration files. Otherwise, the data workbench server generates an error. </p> <p> Processing stages provide a way to order the transformations that are defined within multiple dataset include files. For all of the dataset include files associated with a particular processing stage, transformations are ordered based on their inputs and outputs. In addition, if multiple dataset include files within a stage output data to the same field as a result of a transformation, the data workbench server generates an error. </p> <p> For more information about stages, see <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Log Processing Configuration File</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> Transformation Configuration File</a>, and <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include Files</a>. </p> <p>A <span class="wintitle"> Transformation Dependency Map</span> can display how a field is modified by a series of transformations. See <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Dataset Configuration Tools</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output names </td> 
   <td colname="col2"> Most transformations specify an output field. If the output is a user-defined extended field, the name for this field must start with "x-." The output field names cannot contain spaces or special characters. The names of extended fields can be written with mixed-case, such as "x-NewCampaignName," or "x-New-Campaign-Name" for readability, but they are treated by the software as case-insensitive. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input fields </td> 
   <td colname="col2"> <p>Input fields refer to one of the baseline fields or a user-created field resulting from the output of a previous transformation. If a constant string is needed, a quoted string can be used instead of a baseline or user-created field. </p> <p> For a list of some of the commonly defined fields of data that the data workbench server can process, see <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Event Data Record Fields</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple strings and vectors of strings </td> 
   <td colname="col2"> All transformations operate on strings and/or vectors of strings. Simple strings are literal sequences of characters. String vectors contain zero or more simple strings in a specific order. </td> 
  </tr> 
 </tbody> 
</table>
