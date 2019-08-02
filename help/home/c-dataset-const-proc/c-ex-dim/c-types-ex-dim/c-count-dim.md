---
description: A countable dimension's elements can be counted by the system.
seo-description: A countable dimension's elements can be counted by the system.
seo-title: Countable Dimensions
solution: Analytics
title: Countable Dimensions
topic: Data workbench
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
index: y
internal: n
snippet: y
---

# Countable Dimensions{#countable-dimensions}

A countable dimension's elements can be counted by the system.

 Countable dimensions are typically used to create sum metrics, which return the count, or sum, of all the elements of the dimension. You can define countable dimensions to count instances such as reservation bookings or product orders. For example, you could define the countable dimension Orders whose elements (log entries corresponding to orders from your online store) could be counted. If you want to show a count of orders within a visualization, you would define the Orders sum metric, which can be evaluated over a dimension or have filters applied to it.

Countable dimensions can be parents of other dimensions or children of other countable dimensions.

>[!NOTE]
>
>If you need a dimension that only provides a count of something, you should use a numeric dimension with an operation of COUNT. See [Numeric Dimensions](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

Countable dimensions are defined by the following parameters:

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Default </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Descriptive name of the dimension as appears to the user in data workbench. The dimension name cannot include a hyphen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Comments </td> 
   <td colname="col2"> Optional. Notes about the extended dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> The conditions under which the input field contributes to the creation of the countable dimension. If specified, a condition restricts the set of log entries visible to the dimension and all of its children in the dataset schema. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Hidden </td> 
   <td colname="col2"> Determines whether the dimension appears in the data workbench interface. By default, this parameter is set to false. If, for example, the dimension is to be used only as the basis of a metric, you can set this parameter to true to hide the dimension from the data workbench display. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Key </td> 
   <td colname="col2"> <p>Optional. The name of the field to use as the key. If you define this parameter, an element of the countable dimension exists for every combination of an element of the countable dimension's parent and a distinct value of the field specified as the key. </p> <p> Each element of the countable dimension is required to relate to a contiguous set of log entries. Therefore, if the log entries are not ordered by the key, an element of the countable dimension is created each time the key field changes. To prevent this situation, Adobe recommends that you use a unique key which is contiguous in time order. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>The name of the parent dimension. Any countable dimension can be a parent dimension. To make a dimension the top-level dimension in the dataset's schema, set the parameter to "root." The defined dimension becomes the root countable dimension for the dataset. For example, if you are working with Site, the Visitor dimension is the root countable dimension for your dataset. </p> <p> <p>Note:  Although your root countable dimension does not have to be associated with the tracking IDs in the data, Adobe recommends that you configure your dataset's root countable dimension to use the tracking ID field (x-trackingid) as its Key. As a result, each element of the root countable is associated with a unique value of x-trackingid, and all of the data about each element is grouped together. If you would like to configure your dataset differently, contact Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

This example illustrates the definition of a countable dimension using event data collected from website traffic. The countable dimension counts the web campaign events within a given session. The assumption is that all email campaign resources are requested from the web server with "email=" as part of cs-uri-query. In the example, the number of times that the visitor responds to an email campaign during a given session is of interest, not the actual value of the cs-uri-query(email) field.

![](assets/cfg_Transformation_Dim_Countable.png)

This example also illustrates the definition of a countable dimension using event data collected from website traffic, but it has a defined Key parameter. The Session countable dimension uses the x-session-key field as its key. (The x-session-key field is the output of the [!DNL Sessionize] transformation and has a unique value for each session.) Every unique combination of an element of the Visitor dimension (the parent) and the x-session-key field is an element of the Session dimension.

![](assets/cfg_Transformation_Dim_Countable2.png)

