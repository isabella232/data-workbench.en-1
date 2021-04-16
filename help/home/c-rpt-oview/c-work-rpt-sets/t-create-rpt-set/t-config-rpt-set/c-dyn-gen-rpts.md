---
description: You can generate reports dynamically for the dimension elements that you specify in a lookup file or for a particular number of the dimension elements, such as for the users with the 10 highest order counts.
title: Dynamically Generating Reports
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
---
# Dynamically Generating Reports{#dynamically-generating-reports}

You can generate reports dynamically for the dimension elements that you specify in a lookup file or for a particular number of the dimension elements, such as for the users with the 10 highest order counts.

>[!NOTE]
>
>Adobe discourages the creation of dynamic report sets for daily (or more frequent) report generation. Dynamic report generation can be resource-intensive if you configure reports with large or complex queries.

* [Lookup File Dimension Element Reports](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6) 
* [Top Dimension Element Reports](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Lookup File Dimension Element Reports {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

To configure a report set to dynamically generate and (optionally) distribute reports for the elements of a dimension specified in a lookup file, specify the following parameters in the [!DNL Report.cfg] file:

* [!DNL Dimension Name] 
* [!DNL Lookup File]

For detailed descriptions of these parameters, see [Report.cfg Parameters](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**To create a dynamic report set using a lookup file**

1. Create a two-column lookup file for a given dimension. This file must contain two tab-delimited columns, without a header row.

    * Column 1 should contain a list of dimension elements. 
    * Column 2 should contain the email addresses of the report recipients. A report for a given element in column 1 is sent to the email address(es) on the same row in column 2. You can enter multiple email addresses by separating them with commas (no spaces).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * If reports are not to be emailed, column 2 can be empty but must exist. 
      >    * This file may contain blank lines. 
      >    
      >

1. Optional. To enable the emailing of reports, you must do the following in the [!DNL Mail Report] section of the [!DNL Report.cfg] file for that particular report set:

    * In the SMTP Server parameter, list the appropriate SMTP server to be used to distribute reports via email. 
    * In the Recipients parameter, list at least one email address to enable the reports to be distributed via email. The reports are not mailed to the address listed—you set this parameter only to allow the reports to be emailed. This can be a bogus address, but it must be in an allowable format (for example, [!DNL jsmith@company.com]).

1. Save the lookup file to the report set’s folder. 
1. Open the [!DNL Report.cfg] file for the report set. 
1. In the Dimension Name parameter, type the name of the dimension for which you want to dynamically generate a report. 
1. In the Lookup File parameter, type the location and name of the lookup file containing the dimension elements that you want in the report and the recipient email addresses. 
1. Repeat these steps for additional report sets.

>[!NOTE]
>
>Dynamic reports are not emailed to recipients until the entire report set is complete.

## Top Dimension Element Reports {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

To configure a report set to dynamically generate reports for the top dimension elements, counting by the specified metric, specify the following parameters in the [!DNL Report.cfg] file:

* Dimension Name 
* Top N Metric 
* Top N Value 
* (Optional) Preload Query Filter

For detailed descriptions of these parameters, see [Report.cfg Parameters](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**To create a dynamic report set for the top elements**

1. Open the report set’s [!DNL Report.cfg] file. 
1. In the Dimension Name parameter, type the name of the dimension for which you want to dynamically generate a report set. 
1. In the Top N Metric parameter, type the name of the metric by which you want to sort the dimension. 
1. In the Top N Value parameter, type the number of dimension elements that you want in the report set. 
1. (Optional) In the Preload Query Filter parameter, type the name of the desired filter. 
1. Repeat these steps for additional report sets. 
1. For information about using a dynamic title visualization with your report, see the *Data Workbench User Guide*.
