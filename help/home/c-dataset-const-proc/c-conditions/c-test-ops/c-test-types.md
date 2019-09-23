---
description: The Compare condition and Range condition require that you specify the type of comparison to be made for the condition.
seo-description: The Compare condition and Range condition require that you specify the type of comparison to be made for the condition.
seo-title: Test Types for Test Operations
solution: Analytics
title: Test Types for Test Operations
topic: Data workbench
uuid: dc0433dd-a35e-472e-8975-f58347512c11
---

# Test Types for Test Operations{#test-types-for-test-operations}

The Compare condition and Range condition require that you specify the type of comparison to be made for the condition.

 The following table describes the available types ( [!DNL LEXICAL], [!DNL NUMERIC], and [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <desc> 
  <b>Test Types for Test Operations</b> 
 </desc> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Test Type </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span> </p> </td> 
   <td colname="col2"> <p>First turns the input field into an integer. If this is not possible, a value of zero is used. The test returns true only if the resulting integer input value is greater than or equal to the specified minimum value and less than or equal to the specified maximum value. </p> </td> 
   <td colname="col3"> <p>If either of the min or max fields is left blank, the system uses the appropriate min or max value available to 64-bit signed integers. </p> <p> If the min or max value specified in the condition does not successfully parse to an integer value, the system substitutes zero and does not stop processing the dataset. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>First turns the input field into a date. If the input field cannot be turned into a valid date, the condition test returns false. If the field can be turned into a date, the test returns true only if the input date falls on or after the specified minimum date and on or before the specified maximum date. </p> </td> 
   <td colname="col3"> <p>If the min and max dates are not valid, the dataset are not constructed. </p> <p> If the min or max dates are not supplied, the system substitutes appropriately either the min date (Jan 1, 1600) or the max date (sometime in the 24th century). </p> <p> Adobe recommends using one of the following formats for <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> January 1 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> Jan 1 2013 HH:MM:SS GMT </li> 
    </ul> <p> The time zone defaults to GMT if not specified. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p><span class="wintitle"> LEXICAL</span> </p> </td> 
   <td colname="col2"> <p>Returns true only if the input field is lexically greater than or equal to the string specified as the minimum and less than or equal to the string specified in the maximum value. </p> </td> 
   <td colname="col3"> <p>Lexical comparison uses the ASCII value of characters in the strings moving from left to right comparing the characters. For the first character that does not match, the one with the larger ASCII value is considered to be the greater of the two. In the event that one string is shorter than the other, but up until that point all of the characters have been the same, the longer string is considered the greater of the two. If the strings are character for character equivalent and the exact same length, they are considered lexically equivalent. </p> </td> 
  </tr> 
 </tbody> 
</table>

