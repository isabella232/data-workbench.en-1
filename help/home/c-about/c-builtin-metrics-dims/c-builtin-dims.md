---
description: Data workbench includes built-in dimensions.
solution: Analytics
title: Built-in Dimensions
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
---

# Built-in Dimensions{#built-in-dimensions}

Data workbench includes built-in dimensions.

The following table lists the available built-in dimensions for data workbench: 

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Details </th> 
   <th colname="col3" class="entry"> Level </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> None </td> 
   <td colname="col2"> Derived </td> 
   <td colname="col3"> N/A </td> 
   <td colname="col4">Has a single element “” which relates to all elements of all dimensions. Evaluating a metric over None is like evaluating it over no dimension. <p>The <span class="filepath"> Filter [None=“”]</span> is equivalent to <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> One (Hidden) </td> 
   <td colname="col2"> Numeric </td> 
   <td colname="col3"> N/A </td> 
   <td colname="col4">The element “1”, which also has ordinal value <span class="filepath"> = 1</span>, relates to all elements of all dimensions. The One dimension is normally used to construct counts by using this syntax: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

