---
description: Transform functionality (Transform) runs on a data workbench server machine to enable the export of log source data for use by other applications.
title: About Transformation Functionality
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
---
# About Transformation Functionality{#about-transformation-functionality}

Transform functionality (Transform) runs on a data workbench server machine to enable the export of log source data for use by other applications.

 [!DNL Transform] can read [!DNL .vsl] files, log files, XML files, and ODBC data and export the data as [!DNL .vsl] files, text files, or delimited text files that can be used by DataWarehouse loading routines, auditing agencies, or other targets. The data extraction and transformation can be performed on a continuous or other scheduled basis.

>[!NOTE]
>
>Typically, [!DNL Transform] is configured on a data workbench server FSU. However, your implementation may require configuration on an data workbench server DPU. For more information, contact Adobe.

You can view memory usage information for [!DNL Transform] in the Detailed Status interface. For more information, see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

The segment export feature provides another means of exporting data from an Adobe application. [!DNL Transform] enables you to export unprocessed data to an external target, but the segment export feature enables you to output processed data from the dataset and requires that the exported data be defined as a dimension in the dataset. For more information about segment export, see the *Data Workbench User Guide*.
