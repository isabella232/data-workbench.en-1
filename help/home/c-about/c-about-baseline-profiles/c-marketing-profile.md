---
description: The Campaign dimension is defined in the Site Marketing profile to provide campaign analysis capabilities.
seo-description: The Campaign dimension is defined in the Site Marketing profile to provide campaign analysis capabilities.
seo-title: Marketing Profile Dimensions
solution: Analytics
title: Marketing Profile Dimensions
topic: Data workbench
uuid: 839d99af-76fd-4357-967c-326817e850e6
index: y
internal: n
snippet: y
---

# Marketing Profile Dimensions{#marketing-profile-dimensions}

The Campaign dimension is defined in the Site Marketing profile to provide campaign analysis capabilities.

<table id="table_27A4B8247F6D4E18BD61041CED7D8805"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Level </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> Renamed Simple </td> 
   <td colname="col3">Session <p>FIRST ROW operation </p></td> 
   <td colname="col4"> The campaign identifier extracted from a value in the visitor’s first request. </td> 
  </tr> 
 </tbody> 
</table>

**Samples of Custom Marketing Profile Dimensions**

You can incorporate additional dimensions of data for further analysis. These dimensions are added by incorporating additional information into the stream of data that is collected for analysis. For example, the following table contains some of the custom marketing dimensions that have been added in deployments for customers in various industries: 

|  Dimension (Custom)  | Description  |
|---|---|
|  Email Campaign Date  | Parses the campaign date (first value) from email campaign query strings.  |
|  Email Campaign Detail  | Collects the value string attached to the email campaign query string variable.  |
|  Email Campaign Segment  | Parses the campaign segment (third value) from email campaign query strings.  |
|  Email Campaign Type  | Parses the campaign type (second value) from email campaign query strings.  |
|  Marketing Campaign Detail  | Collects the value string attached to marketing campaign query string variables.  |
|  Marketing Campaign Owner  | Parses the campaign owner (fourth value) from marketing campaign query strings.  |
|  Marketing Campaign Source  | Parses the campaign source (first value) from marketing campaign query strings.  |
|  Marketing Campaign Type  | Parses the campaign type (second value) from marketing campaign query strings.  |
|  PPC Campaign Detail  | Collects the value string attached to the ppc query string variable.  |

