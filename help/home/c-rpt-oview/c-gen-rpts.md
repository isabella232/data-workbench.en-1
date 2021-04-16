---
description: Generate reports by processing workspaces and specifying them as reports.
title: Generating Reports
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
---
# Generating Reports{#generating-reports}

Generate reports by processing workspaces and specifying them as reports.

[!DNL Report] generates your reports at the interval set in the [!DNL Every] parameter in the [!DNL Report.cfg] file (such as [!DNL "day]," which processes the report on a daily basis), and based on the other [!DNL Report.cfg] file settings.

While generating reports, the percent complete displays on the [!DNL Reports] tab under the thumbnail for that particular report. If [!DNL Report] encounters a problem during report generation, the most recent error message displays on the [!DNL Reports] tab in the report set’s folder. If [!DNL Report] does encounter an error for a particular report, it continues to process the other reports in the set.

You can generate the reports in a report set in any or all of the following formats using the [!DNL Report Types] parameter in the [!DNL Report.cfg] file:

* Microsoft Excel file ( [!DNL .xls] or [!DNL .xlsx]) 
* Portable network graphic file ( [!DNL .png]) 
* Thumbnail ( [!DNL .jpg])

Along with the types of output specified, [!DNL Report] creates an [!DNL .xml] file named the same as your report. This *`<report name>`*.xml file contains the description of the report that displays in Data Workbench on the [!DNL Reports] tab below the report’s thumbnail. This makes the description available to use when distributing your reports through a reporting portal. For information about the [!DNL Report Portal], see [Working with Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>If you redefine an internal metric, the system behaves unexpectedly because of the wrong value. Your reports will not generate unless a metric reads 100%. It is recommended that you do not change metric definitions.
