---
description: Information to generate reports as Excel files.
solution: Analytics
title: Generating Reports as Microsoft Excel Files
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
---

# Generating Reports as Microsoft Excel Files{#generating-reports-as-microsoft-excel-files}

Information to generate reports as Excel files.

The following requirements must be met:

* Microsoft Excel must be installed on the same machine as [!DNL Report Server]. 
* The user account under which the [!DNL Report Server] process is running must have permission to access Microsoft Excel. 

  >[!NOTE]
  >
  >
  >    
  >    
  >    * When you generate reports as Excel files, you are opening a new instance of Excel. For more information about this process, see [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757). 
  >    * Although data workbench supports more than 256 columns and 65,536 rows of data, Microsoft Excel does not. 
  >    
  >

If these requirements are met, [!DNL Report Server] automatically starts Microsoft Excel and output data from certain visualizations, dimension and value legends, and text annotations to a new Excel workbook with one visualization per worksheet.

>[!NOTE]
>
>Data is not exported from graphs, path browsers, process maps, scatter plots, and globes.

Unless you have specified a [!DNL Custom Title] for the visualization, the type of window (for example, Movie Table) is used as the worksheet name.

For more information about specifying [!DNL Custom Titles] for visualizations, see the [Data Workbench Client Guide](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html).

## Using a Template File {#section-40ab11916f464b1a88214ab969da6751}

You also can generate a report as an Excel file using a template Excel ( [!DNL .xls] or [!DNL .xlsx]) file. Using a template file can reduce the amount of time that you spend formatting your data each time the report is generated.

This template file must be an [!DNL .xls] or [!DNL .xlsx] file, not an [!DNL .xlt] file.

You can choose to define a template for each individual report, a generic template for all of your reports, or a combination of both. These two items are not mutually exclusive, so you can define a generic template and then define specific templates as well.

To generate a report using a generic template that you use for all reports, you must specify the name of that Excel file in the Default Excel Template parameter in the [!DNL Report.cfg] for that report set file, then place the template file in the same folder as the [!DNL Report.cfg] for that report set (*data workbench installation directory*\*ProfileName*\Reports\*ReportSetName*). For information about this parameter, see [Report.cfg Parameters](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

To generate a report using a template that is specific to a report, you must name the Excel file the same as the report workspace ( [!DNL .vw]) file, then place the template file in the same folder as the report workspace ( [!DNL .vw]) file.

When the report is generated, the existing tabbed sheets in the template (each representing one visualization) are repopulated with the most recent data from the report, while any new windows that are not present in the template as tabbed sheets are ignored. Any other tabbed sheets in the template file remain unchanged.

In addition, if you have a macro defined in the template Excel file that you would like to run automatically when the report is generated, name the macro “VSExport.” 
