---
description: Data workbench provides a set of transformations that enables the data workbench server to incorporate lookup data into the dataset.
solution: Analytics
title: Integrating Lookup Data
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
---

# Integrating Lookup Data{#integrating-lookup-data}

Data workbench provides a set of transformations that enables the data workbench server to incorporate lookup data into the dataset.

Lookup data is external data from corporate databases or lookup files that you can combine with event data to create the dataset. In general, you use lookup data to augment the event data from your log sources. Conceptually, you can think of using lookup data to populate event data records with additional columns of information.

When you use lookup data, you load the data into a memory-resident lookup table. A column in the table must contain a common key that also exists in the event data records. The data in the lookup table itself can be loaded from a flat file or from an ODBC data source. Lookup data can be incorporated into the dataset during the log processing or transformation phase of the dataset construction process.

To incorporate lookup data, you must first generate a lookup file or have the information needed to access an SQL database, then define one or more of the following transformations in the dataset configuration files for log processing and transformation.

**To integrate lookup data into the dataset**

1. Generate your lookup file. See [Populating the Lookup Table](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8). 
1. Define one of the following types of transformations in the Transformations parameter in the appropriate dataset configuration file:

    * [!DNL Categorize] 
    * [!DNL FlatFileLookup] 
    * [!DNL ODBCLookup]

>[!NOTE]
>
>Note that the [!DNL ODBCLookup] transformation works only when defined in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file.

