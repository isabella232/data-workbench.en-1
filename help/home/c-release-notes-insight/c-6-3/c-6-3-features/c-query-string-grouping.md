---
description: Query String Grouping lets you integrate a large number of fields together.
seo-description: Query String Grouping lets you integrate a large number of fields together.
seo-title: Query String Grouping
title: Query String Grouping
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
---

# Query String Grouping{#query-string-grouping}

Query String Grouping lets you integrate a large number of fields together.

Query String Grouping is specific to each profile, but works well in transformations as shown in this example:

1. Create the pairs you wish to bundle by adding a custom configuration file ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) and then adding the Transformation Type *BuildNameValuePair* as a parameter. 

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
<b>(all the fields you wish to build)</b> 
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. Create a new file for extracting the condensed data into the fields you wish to use by adding a custom configuration file ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]) and then adding the Transformation Type *ExtractNameValuePairs* as a parameter. 

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
<b>(all the fields you wish to extract)</b> 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## Other Uses {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

If you have many fields with custom evars, props, and variables, during log processing you can build a name value pair to combine fields in a report. For example, you can build named-value pairs into combined fields to reduce the [!DNL tempDB] file size.

![](assets/query_string_grouping.png)

