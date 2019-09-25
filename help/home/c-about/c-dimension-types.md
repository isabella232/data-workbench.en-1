---
description: Several types of dimensions are available in the data workbench server. As such, it is important to know the dimension type when using a dimension to create metrics, filters, or derived dimensions.
seo-description: Several types of dimensions are available in the data workbench server. As such, it is important to know the dimension type when using a dimension to create metrics, filters, or derived dimensions.
seo-title: Dimension Types
solution: Analytics
title: Dimension Types
topic: Data workbench
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
---

# Dimension Types{#dimension-types}

Several types of dimensions are available in the data workbench server. As such, it is important to know the dimension type when using a dimension to create metrics, filters, or derived dimensions.

Insight Server can create and maintain the following types of dimensions:

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension Types </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Countable </td> 
   <td colname="col2">A dimension type in which the number of elements in the dimension can be counted by the system. Countable dimensions must be derived from other Countable dimensions. Countable dimensions can be parents of other dimensions or children of other countable dimensions. <p>Examples: Visitor, Session, Page View, Booking, and Order. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2">A dimension that has a one-to-many relationship with a parent countable dimension. A simple dimension can be thought of as representing a property of elements of its parent dimension. <p>Example: Visitor Referrer is a simple dimension with a parent of the Visitor dimension. Each Visitor can have only one Visitor Referrer (their first HTTP referrer), but many Visitors might have the same Visitor Referrer. Therefore the Visitor Referrer is “one-to-many” with the Visitor dimension. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeric </td> 
   <td colname="col2">A dimension that has ordered, numerical values and a one-to-many relationship with a parent countable dimension. A numeric dimension can be thought of as representing a numeric property of elements of its parent dimension. Numeric dimensions are often used to define “sum” metrics. <p>Example: The numeric dimension Session Revenue defines the revenue, in dollars, for each Session. Each Session has a single amount of revenue, but any number of Sessions might have the same revenue, so Session Revenue is “one-to-many” with Session. A metric “Revenue” might be defined as <span class="filepath"> sum(Session_Revenue, Session)</span>, giving the total amount of revenue for the selected Sessions. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Many-to-Many </td> 
   <td colname="col2">A dimension that has a many-to-many relationship with a parent countable dimension. A many-to-many dimension can be thought of as representing a “set” of values for each element of its parent dimension. A many-to-many dimension is equivalent to an (anonymous) countable dimension with its parent and a Simple dimension with a parent of the anonymous countable dimension. <p>Example: The many-to-many dimension Search Phrase has a parent of Session. Each Session can use zero or more Search Phrases, and a Search Phrase can be used in any number of Sessions. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">A dimension that has a one-to-one relationship with a parent Countable dimension. The element names of the denormal dimension can carry information about the corresponding elements of the parent dimension. A denormal dimension can be thought of as storing an arbitrary string value for each element of the parent. Denormal dimensions can be used with Insight Server’s segment export capability to output details about a subset or “segment” of a countable dimension. In addition, denormal dimensions can be referenced in metric formulas and worksheet visualizations and can be used (with certain restrictions) to define filters. <p>Example: The denormal dimension EMail Address has a parent of Visitor. Each Visitor has an EMail Address, and each element of the EMail Address dimension is associated with a single Visitor. Even if two visitors have the same e-mail address, their addresses will be different elements of the EMail Address dimension. A Segment Export can reference the EMail Address dimension to output the EMail Address of each visitor in a Segment. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time </td> 
   <td colname="col2">A dimension that enables you to create a set of periodic or absolute local time dimensions (such as Day, Day of Week, Hour, Hour of Day, and so on) based on a timestamp field that you specify. When defining time dimensions, you also can choose a day other than Monday to be used as the start of a week by specifying the Week Start Day parameter. <p>Example: The time dimension Session Time has parent of Session. Therefore, the dimension defines a set of time dimensions (Day, Day of Week, Hour, Hour of Day, Month, and Week) whose elements correspond to the times at which visitors’ sessions on the site began. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derived </td> 
   <td colname="col2">Derived dimensions, rather than being defined in the dataset configuration based on the data being processed, are defined in the profile based on other dimensions or metrics. Many derived dimensions are created automatically to drive different types of visualizations. <p>Example, when a user builds a site or process map, Insight Server silently creates a “Prefix” dimension. Others, such as the reporting time dimensions, are defined by files in the Dimensions directory of a profile. </p></td> 
  </tr> 
 </tbody> 
</table>

