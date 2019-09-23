---
description: After the reports have been generated, Report distributes the reports in the set based on the settings in its Report.cfg file.
seo-description: After the reports have been generated, Report distributes the reports in the set based on the settings in its Report.cfg file.
seo-title: Distributing Reports
solution: Analytics
title: Distributing Reports
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
---

# Distributing Reports{#distributing-reports}

After the reports have been generated, Report distributes the reports in the set based on the settings in its Report.cfg file.

 [!DNL Report] enables you to distribute the reports in a set using the following methods:

* **Email:** To distribute reports as Excel files, [!DNL .png] files, or thumbnails via email (in-line or as attachments), specify the Mail Report parameters in the report set’s [!DNL Report.cfg] file. All reports in that set are emailed in one message to the specified recipients. 

* **Shared Directory:** To distribute reports as Excel files, [!DNL .png] files, or thumbnails to a shared directory, specify the directory in the Output Root parameter in the report set’s [!DNL Report.cfg] file. 

* **Reporting Portal:** A reporting portal enables you to view reports through your web browser. Adobe’s [!DNL Report Portal] displays reports generated as Excel or [!DNL .png] files, but not those generated as thumbnails ( [!DNL .jpg]). To distribute reports to a portal, specify the document root of the web server used for the portal in the Output Root parameter in the report set’s [!DNL Report.cfg] file. For more information about installing and using [!DNL Report Portal], see [Working with Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>To read the output that is currently supported by [!DNL Report], you must have an application capable of displaying the reports in the desired format(s). For example, to view [!DNL .xlsx] files, you must have Microsoft Excel 2007 or later.

You can also use a combination of these generation and distribution options. For example, if you set the [!DNL Report Types] parameter to generate a report set as Excel and [!DNL .png] files, and then set the [!DNL Mail Report]and [!DNL Output Root] parameters, all of the reports in that set are distributed to the specified output directory (perhaps to be viewed in a portal) and emailed in one email to recipients.

For steps to configure your report sets, see [Working with Report Sets](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). For more information about the specific [!DNL Report.cfg] parameters, see [Report.cfg Parameters](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff). 
