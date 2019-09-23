---
description: Steps to edit existing Report.cfg files using Worktop or a text editor.
seo-description: Steps to edit existing Report.cfg files using Worktop or a text editor.
seo-title: Editing Existing Report.cfg Files
solution: Analytics
title: Editing Existing Report.cfg Files
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
---

# Editing Existing Report.cfg Files{#editing-existing-report-cfg-files}

Steps to edit existing Report.cfg files using Worktop or a text editor.

>[!NOTE]
>
>* You must be working online to edit [!DNL Report.cfg] files. To work online, from the [!DNL Worktop], right-click the title bar and click **[!UICONTROL Work Online]**. 
>
>* If the **[!UICONTROL Allow Report Regeneration]** parameter in the [!DNL Report.cfg] file is set to [!DNL True], when you make changes to that file and save that file back to the server, [!DNL Report] automatically re-generates the reports in that set. Although it regenerates the reports, it does not re-send the reports via email. For steps to do so, see [Resending Reports by Email](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607). 
>

You can edit an existing [!DNL Report.cfg] from the [!DNL Worktop] or using a text editor.

Editing a [!DNL Report.cfg] file using the [!DNL Reports] tab of the [!DNL Worktop] enables you to edit only those parameters, vectors, and vector items that already exist in the file. If you need to add a parameter or vector to the file, you must edit it using a text editor, such as Notepad.

* [To edit an existing Report.cfg using the Worktop](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945) 
* [To edit an existing Report.cfg using a text editor](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## To edit an existing Report.cfg using the Worktop {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>You must be working online to edit the [!DNL Report.cfg] from the [!DNL Worktop].

1. In data workbench, on the [!DNL Reports] tab, select the subfolder (tab or drop-down subdirectory) for the report set that you want to configure. 
1. Click **[!UICONTROL Report.cfg]**. The parameters of the [!DNL Report.cfg] for this report set display. 

1. Edit the configuration parameters as desired. For information about these parameters, see [Report.cfg Parameters](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff). 
1. Save the file by right-clicking **[!UICONTROL Report.cfg (modified)]** at the top of the parameters and clicking **[!UICONTROL Save to]***< **[!UICONTROL server location]**>*.

## To edit an existing Report.cfg using a text editor {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Open the [!DNL Reports Manager] by right-clicking within a workspace and clicking **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**. 

1. Click the folder for your report set. 
1. Right-click the check mark next to the [!DNL Report.cfg] for this report set and click **[!UICONTROL Make Local]**. 

1. In the [!DNL User] column, right-click the check mark next to [!DNL Report.cfg] for this report set and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Report.cfg] file opens.

   The sample [!DNL Report.cfg] shown in [Configure the Report Set](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contains only the parameters included in the [!DNL Report.cfg] file by default. The following example includes all of the parameters available for the [!DNL Report.cfg] file that you can use as models for your parameter entries: 

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Edit the configuration parameters as desired. For information about these parameters, see [Report.cfg Parameters](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff). 
1. Save and close the file. 
1. In the [!DNL Reports Manager], right-click the check mark in the [!DNL User] column for the [!DNL Report.cfg] file and select **[!UICONTROL Save to]***< **[!UICONTROL profile name]**>*.

