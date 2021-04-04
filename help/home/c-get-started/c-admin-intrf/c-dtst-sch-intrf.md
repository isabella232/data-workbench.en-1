---
description: The Dataset Schema interface displays the extended dimensions (countable, simple, many-to-many, numeric, denormal, and time dimensions) defined in any transformation dataset configuration file and provides a view of the relationships between those dimensions.
solution: Analytics
title: Dataset Schema interface
topic: Data workbench
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
---
# Dataset Schema interface{#dataset-schema-interface}

The Dataset Schema interface displays the extended dimensions (countable, simple, many-to-many, numeric, denormal, and time dimensions) defined in any transformation dataset configuration file and provides a view of the relationships between those dimensions.

 In addition, the [!DNL Dataset Schema] interface shows any derived dimensions that you have defined, as well as any extended dimensions that are configured to be hidden.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>You can search for dimensions from within the schema diagram. The name of the dimensions found by the search string are highlighted, and the lines of the parent class change color for any hits found in subordinate child dimensions. The Countable dimensions stay visible as you scroll to provide viewable hierarchy and context.

**To interpret a dimension type using the [!DNL Dataset Schema] interface**

The following table lists the dimension types and the colors in which their names appear in the [!DNL Dataset Schema] interface. Parents for the sample dimensions (from the example above) are noted as well.

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension Type </th> 
   <th colname="col2" class="entry"> Color </th> 
   <th colname="col3" class="entry"> Sample Dimension and Parent </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Countable </td> 
   <td colname="col2"> Pink </td> 
   <td colname="col3"> <p>Visitor - In this schema, Visitor is a root countable dimension. </p> <p>Session - parent is Visitor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Yellow </td> 
   <td colname="col3"> DenormalPage - parent is Page View </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derived </td> 
   <td colname="col2"> Blue </td> 
   <td colname="col3"> Next Page - parent is Page View </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Many-to-Many </td> 
   <td colname="col2"> Pink and Green (The stem from the parent is pink, while the dimension name is green.) </td> 
   <td colname="col3"> Search Term - parent is Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeric </td> 
   <td colname="col2"> Green </td> 
   <td colname="col3"> Exact Page Duration - parent is Page View. In this example, Exact Page Duration is a hidden numeric dimension. See the Hidden dimension type in this table. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2"> Green </td> 
   <td colname="col3"> Page - parent is Page View </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time </td> 
   <td colname="col2"> Green </td> 
   <td colname="col3"> Hour - parent is Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden </td> 
   <td colname="col2"> Hidden dimensions are a darker version of the appropriate dimension type color. For example, a hidden numeric dimension is a darker, less bright green. </td> 
   <td colname="col3"> Exact Page Duration - parent is Page View </td> 
  </tr> 
 </tbody> 
</table>

For more information about these dimension types, see the *Dataset Configuration Guide*.

**To display the default visualization for a dimension**

* In the [!DNL Dataset Schema] interface, click the desired dimension. The default visualization displays. For example, if the default visualization is a table displaying Sessions and the selected dimension and you click the URI dimension, Data Workbench displays a table with URI by Sessions.

  >[!NOTE]
  >
  >If you want to change the default visualization that displays, see [The Dataset Schema Interface](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**To display a specific visualization for a dimension**

* In the [!DNL Dataset Schema] interface, right-click the desired dimension and click **[!UICONTROL Add Visualization]** > *< **[!UICONTROL visualization type]**>*.
