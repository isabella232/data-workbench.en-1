---
description: Data workbench utilizes regular expressions (regex) for search and sort operations.
solution: Analytics
title: Regular expressions
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
---

# Regular expressions{#regular-expressions}

Data workbench utilizes regular expressions (regex) for search and sort operations.

Within the **[!UICONTROL Search]** field you can perform a search following the "re:" statement using common expressions, for example:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metacharacter </th> 
   <th colname="col2" class="entry"> description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. (dot) </p> </td> 
   <td colname="col2"> <p>Matches a single character, for example: <span class="filepath"> re:x.z </span> matches "xyz" or "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (star) </p> </td> 
   <td colname="col2"> <p>Matches one or more characters, for example: <span class="filepath"> re:Z* </span> matches "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (wildcard) </p> </td> 
   <td colname="col2"> <p>Matches 0 or 1 of previous expression to force minimal matching, for example: <span class="filepath"> xy?z </span> matches "xy" and "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

Additional common regular expressions can also be used to create more complex search strings. Regular expressions are used across all Data Workbench search fields including the query entity panels.

See in-depth information at [regular expressions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions). 
