---
description: If you use the Categorize or FlatFileLookup transformations, the lookup table is loaded in memory and populated from a flat file whose location you specify when you define the transformation.
solution: Analytics
title: Populating the Lookup Table
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
---
# Populating the Lookup Table{#populating-the-lookup-table}

If you use the Categorize or FlatFileLookup transformations, the lookup table is loaded in memory and populated from a flat file whose location you specify when you define the transformation.

The flat file you specify must meet the following requirements:

* Each line in the file must represent a row in the lookup table. 
* Columns in the file must be separated by an ASCII delimiter. You may use any character that is not a line-ending character and does not appear anywhere within the event data itself. When you define the transformation, you specify which character has been used to delimit the columns in the flat file.

If you use an [!DNL ODBCLookup] transformation, the lookup table is loaded into memory and populated from a table or view in an [!DNL ODBC] database that you specify. When you define the transformation, you must also specify the data source, user name, and password that the data workbench server must use to establish a connection to the database.

>[!NOTE]
>
>Lookup tables are loaded when the data workbench server initially begins constructing the dataset. Once established, lookup files are not meant to be changed. If you change the flat file or [!DNL ODBC] table that is used for the transformation phase, you are required to retransform the entire dataset. If you change a flat file that is used during the log processing phase, the new lookup data is applied to all new records that enter the dataset, but the changes are not applied retroactively.
