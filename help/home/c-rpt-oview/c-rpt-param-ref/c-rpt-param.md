---
description: Information about Report.cfg parameters.
solution: Analytics
title: Report.cfg Parameters
topic: Data workbench
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
---

# Report.cfg Parameters{#report-cfg-parameters}

Information about Report.cfg parameters.

The sample [!DNL Report.cfg] shown in [Configure the Report Set](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contains only the parameters included in the [!DNL Report.cfg] file by default. The following table provides descriptions of all of the available [!DNL Report.cfg] file parameters.

If you need to add additional parameters to a [!DNL Report.cfg] file, you must do so using a text editor. For steps to do so, including examples of how to define each parameter entry, see [Editing Existing Report.cfg Files](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>The parameters in this table are listed in alphabetical order. When you open the [!DNL Report.cfg] file in Data Workbench, vectors are listed in alphabetical order, followed by individual parameters listed in alphabetical order.

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Alert Threshold </td> 
   <td colname="col2"> <p><i>Optional</i>. This parameter applies only to reports with metric indicators. Number of metric indicators that must appear in the worksheet before an alerting report is sent. </p> <p>If only one metric is being monitored in the metric indicator worksheet, set the threshold to 1. The report is generated when the metric in the sheet evaluates to an up/down arrow or an X. If more than one metric is being monitored in the report, you can select the number of metric indicators that must evaluate to an up/down arrow or an X before the report is generated. For example, if two metrics are being monitored: 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">If the threshold is set to 1, the report is generated if either of the metrics in the sheet evaluate to an up/down arrow or an X. </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">If the threshold is set to 2, both of the metrics must evaluate to an up/down arrow or an X before the report is generated. </li> 
     </ul> </p> <p>For more information about metric indicators, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allow Report Regeneration </td> 
   <td colname="col2"> <p>Indicates whether <span class="keyword"> Report Server </span> automatically generates or regenerates particular reports when you create or modify those reports. The options are true or false. If set to true, creating or modifying a report workspace causes <span class="keyword"> Report Server </span> to regenerate that report for the most recent run. </p> <p> <p>Note:  Changing the <span class="filepath"> Report.cfg </span> file causes <span class="keyword"> Report Server </span> to regenerate all reports controlled by that <span class="filepath"> Report.cfg </span> file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Attachments </td> 
   <td colname="col2"> <p><i>Optional</i>. Section identifier for the name and content type of any attachments that go out with reports distributed via email, including the number of attachments. </p> <p>To add a new attachment: 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Open the <span class="filepath"> Report.cfg </span> file in Data Workbench. </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Right-click <span class="uicontrol"> Attachments </span> and click <span class="uicontrol"> Add new child </span> &gt; <span class="uicontrol"> Attachment </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Content Type </td> 
   <td colname="col2"> <p>Content type of the file to be attached. </p> <p>Example: image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FileName </td> 
   <td colname="col2"> <p>Location and name of the file to be attached. </p> <p>Example: <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color Set </td> 
   <td colname="col2"> Identifies the color scheme to be used for <span class="filepath"> .png </span> files. 0 is for a black background; 1 is for a white background; and 2 is for a grayscale image. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Command To Execute </td> 
   <td colname="col2"> <i>Optional</i>. A batch command or executable that runs after the report set is generated. If launch of the command shell interpreter is required, precede the command with cmd /c. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Default Excel Template </td> 
   <td colname="col2"> <p><i>Optional</i>. File name of the generic Excel template file ( <span class="filepath"> .xls </span> or <span class="filepath"> .xlsx </span>) that you want to use when generating reports as Excel files. This parameter supports full file paths, such as <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>This file is used for all Excel reports unless a template has been defined specifically for a particular report. See <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Using a Template File </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension Name </td> 
   <td colname="col2"> <i>Optional</i>. Name of the dimension for which you want to dynamically generate a report. If you enter a dimension name in this parameter, you must enter a value in either the Lookup File parameter or the Top N Metric and Top N Value parameters. The dimension named in this parameter must exist in the dataset for which reports are being created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Email Only If Perfect </td> 
   <td colname="col2"> <i>Optional</i>. Lets the user specify that a report set should be sent out only when no errors occurred during the run. The options are true and false. The default value is false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> End Date </td> 
   <td colname="col2"> <p><i>Optional</i>. The last date and time that you want the report set to run. This time is based on the As Of time of the dataset. </p> <p>Format: MM/DD/YYYY hh:mm time zone, using the 24-hour syntax for time </p> <p>Example: 08/01/2007 12:01 EDT </p> <p>For more information about time zone settings, see the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Every </td> 
   <td colname="col2"> Frequency of the report set generation: day, week, or month. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excel Watchdog Timeout (seconds) </td> 
   <td colname="col2"> <p><i>Optional</i>. The number of seconds that you want <span class="keyword"> Report Server </span> to wait for Microsoft Excel to respond when generating a report as an Excel file before <span class="keyword"> Report Server </span> decides that Excel is not responding and terminates the process. Using this parameter enables <span class="keyword"> Report Server </span> to terminate Excel when it becomes unresponsive and continue processing your non-Excel reports. The default is 300.0. To disable this functionality, set this parameter to 0.0. </p> <p>Make sure that the value you define is long enough to allow the report to be exported to Excel. Otherwise, <span class="keyword"> Report Server </span> may prematurely terminate Excel and your report will not generate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter Formula </td> 
   <td colname="col2"> <p><i>Optional</i>. Filter that is applied to every workspace in the report set. </p> <p>For more information, see the <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> syntax for creating filters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma Correction </td> 
   <td colname="col2"> <p>Gamma setting for <span class="filepath"> .png </span> file output. The default is 1.6. </p> <p> <p>Note:  Adobe recommends that you do not change this value. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hide Logos </td> 
   <td colname="col2"> Indicates whether Report Server hides the logos when generating your reports. The options are <span class="filepath"> true </span> or <span class="filepath"> false </span>. If set to <span class="filepath"> false </span>, your report is generated with the Report logo. The default is <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lookup File </td> 
   <td colname="col2"> <p><i>Optional</i>. When this parameter is populated, Report Server runs in dynamic mode and generates reports for each element of the dimension specified in the Dimension Name parameter. This file must contain two tab-delimited columns, without a header row. </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">Column 1 contains a list of dimension elements. </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">Column 2 contains the email addresses of the report recipients. A report for a given element in column 1 is sent to the email address on the same row in column 2. You can enter multiple email addresses by separating them with commas (no spaces). If reports are not to be emailed, this column can be empty but must exist. </li> 
     </ul> </p> <p> <p>Note:  If you enter a value in this parameter, you must enter a value in the Dimension Name parameter. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Notification Only </td> 
   <td colname="col2"> This <span class="wintitle"> Report Server </span> setting allows you to configure data workbench to send an email when a report is generated. Setting this value to <span class="filepath"> true </span> does not send out the report, but rather sends an email notifying the subscribed user that the report has been generated. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mail Report </td> 
   <td colname="col2"> <p>Section identifier for distributing reports via email. To distribute reports via email, complete the following parameters for the <span class="wintitle"> Mail Report </span> entry. All reports in the report set are emailed in one message to the email addresses specified in the Recipients parameter. </p> <p> <p>Note:  Report Server sends an email only when it has generated at least one report. </p> </p> <p>To enable the emailing of reports, you must complete at least the following parameters for this entry: 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP Server </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Recipients </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Sender Address </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Notification Only </li> 
     </ul> </p> <p> <p>Note:  To send out reports by email after re-generating a report set, see <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Editing Existing Report.cfg Files </a>. </p> </p> <p>The Notification Only value is available in 5.4x and 5.5x releases. </p> <p>For a large set of recipients to be notified (more than 20), it is highly recommended that you use email distribution lists. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Body XSL Template </td> 
   <td colname="col2"> <p><i>Optional</i>. Path of the XSL template file to be applied to the <span class="filepath"> reports.xml </span> file. Using this parameter enables Report Server to send your reports within the distributed email instead of as attachments. The resulting text is used as the body of the email message. </p> <p>See <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Report Sample Files </a> for a sample file. </p> <p>For information about Extensible Stylesheet Language (XSLT), see <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> The Extensible Stylesheet Language Family </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recipients </td> 
   <td colname="col2"> Email addresses of the people to whom you want to send the report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sender Address </td> 
   <td colname="col2"> Email address of the sender. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sender Name </td> 
   <td colname="col2"> Optional. Name of the sender. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server </td> 
   <td colname="col2"> Address of the SMTP server machine and the password and user name required for authentication. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Subject </td> 
   <td colname="col2"> <i>Optional</i>. Subject line describing the email to be sent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Notification Only </td> 
   <td colname="col2"> Lets you configure data workbench to send an email when a background report is generated. Setting this value to True does not send out the report, but rather sends an email linking the subscribed user to the report location. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Root </td> 
   <td colname="col2"> <p><i>Optional</i>. Output location of the generated report sets. The default is the <i>&lt;profile name&gt;</i>\Reports folder within the Report Server installation directory. </p> <p>To configure <span class="keyword"> Report Server </span> to output reports to a portal, set the <span class="wintitle"> Output Root </span> to the document root of the web server used for the portal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Preload Query Filter </td> 
   <td colname="col2"> <p><i>Optional</i>. This parameter applies only to the <span class="wintitle"> Top Dimension Element </span> report type. </p> <p>The name of the filter that you want to apply to the query that must be run to determine the top N dimension elements before the report can be generated. The default is <span class="wintitle"> Broken_Session_Filter </span>. For more information about the <span class="wintitle"> Broken Session Filter </span>, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Report Types </span> </td> 
   <td colname="col2"> <p>Format(s) in which you want to generate your output. You can use any or all of the following options to output the report set in multiple formats at one time: 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel creates an Excel workbook with one visualization per worksheet. As a general rule, use Excel files for email distribution. See <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Generating Reports as Microsoft Excel Files </a>. For information about using a template file, see <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Using a Template File </a>. </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png creates Portable Network Graphic files. As a general rule, use <span class="filepath"> .png </span> files for display in a web browser (portal). </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">Thumbnail creates a thumbnail ( <span class="filepath"> .jpg </span> file) of the workspace. The default size is 240x180. To change the default size, edit the Thumbnail X and Thumbnail Y parameters. </li> 
     </ul> </p> <p>To add a new report type when editing <span class="filepath"> Report.cfg </span> in data workbench, right-click <span class="uicontrol"> Report Types </span>, click <span class="uicontrol"> Add new child </span>, and select the desired report type. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Start Date </td> 
   <td colname="col2"> <p>The first date and time that you want the report set to run. This time is based on the As Of time of the dataset. </p> <p>Format: MM/DD/YYY hh:mm time zone, using the 24-hour syntax for time. </p> <p>For more information about time zone settings, see the <i>Dataset Configuration Guide</i>. </p> <p> <p>Note:  The reports start to run when the timestamps of the data in the profile match the date and time specified. </p> </p> <p>Example: </p> <p>If the start date is 08/08/2006 12:00 EST, reports run for data with a timestamp of 08/08/2006 12:00 EST and later. 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">Daily reports will run for 08/08/2006 and each day thereafter for data with hh:mm = 12:00 EST. </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">Weekly reports will run for 08/08/2006 and for every 7th day thereafter for data with hh:mm = 12:00 EST. </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">Monthly reports will run for 08/08/2006 and for the 8th day of each month thereafter for data with hh:mm = 12:00 EST. </li> 
     </ul> </p> <p>The <span class="wintitle"> Report Time </span> metric affects “Last N” reporting dimensions, such as “Last 7 Days,” “Yesterday,” and “3 weeks ago.” For queries in Report Server, the <span class="wintitle"> Report Time </span> metric ( <span class="filepath"> Report Time.metric </span>) identifies the date and time for which the reports are being run. This is initially the date and time specified in the Start Date parameter, which then increments by the period specified by the Every parameter. For queries in data workbench, the <span class="wintitle"> Report Time </span> metric is based on midnight of the As Of metric ( <span class="filepath"> As Of.metric </span>). Because of the difference in the definitions of the Report Time metric, if you query a workspace that uses a Last N dimension, you can receive different results in data workbench and <span class="keyword"> Report Server </span> for the same workspace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Thumbnail X </td> 
   <td colname="col2"> <i>Optional</i>. Integer controlling the size (in pixels) of the X axis of thumbnails generated as output. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Thumbnail Y </td> 
   <td colname="col2"> <i>Optional</i>. Integer controlling the size (in pixels) of the Y axis of thumbnails generated as output. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Top N Metric </td> 
   <td colname="col2"> <p><i>Optional</i>. See the description for the Top N Value parameter. </p> <p> <p>Note:  If you enter a value in this parameter, you must enter a value in the Dimension Name parameter and the Top N Value parameter. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Top N Value </td> 
   <td colname="col2"> <p><i>Optional</i>. When this parameter is populated, <span class="keyword"> Report Server </span> runs in dynamic mode and generates reports for the top number (specified in this parameter) of elements for the dimension specified in the Dimension Name parameter, counting by the metric specified in the Top N Metric parameter. </p> <p>Example: If you enter Page in the Dimension Name parameter, Sessions in the Top N Metric parameter, and 5 in this parameter, the generated report lists the five top pages with the highest number of sessions. </p> <p> <p>Note:  If you enter a value in this parameter, you must enter a value in the Dimension Name parameter and the Top N Metric parameter. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use Local Sample Only </td> 
   <td colname="col2"> <i>Optional</i>. Indicates whether you want <span class="keyword"> Report Server </span> to generate reports using only the local sample of the dataset. Setting this parameter to true enables you to view a sample of the report set (without placing a load on a data workbench server) to see how the output looks without taking all the time needed to fully process the data. This operates as a test function. The options are true or false. The default is false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Workspace Path </td> 
   <td colname="col2"> <p><i>Optional</i>. Location of a collection of workspaces for a given report set. This is useful for maintaining a single copy of workspaces that need to be generated and distributed multiple ways, using <span class="filepath"> Report.cfg </span> files for multiple report sets. The root directory for this path can be any profile folder. Do not enter a slash (\) at the start of the path string. </p> <p>Example: You can save the common workspaces for Set A and Set B in the <span class="filepath"> Reports\Common </span> folder, then define the <span class="filepath"> Report.cfg </span> files for two different report sets, each with different generation and distribution settings. In both <span class="filepath"> Report.cfg </span> files, you would set the Workspace Path parameter to <i>profile name</i>\Reports\Common. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL Output File </td> 
   <td colname="col2"> <i>Optional</i>. Path of the output file that is created when the <span class="wintitle"> XSL Template </span> is applied to the report index. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL Template </td> 
   <td colname="col2"> <p><i>Optional</i>. Path of the XSL template file to be applied to the report index. The resulting transformed <span class="filepath"> .xml </span> is written to the specified <span class="wintitle"> XSL Output File </span>. See <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Report Sample Files </a> for a sample file. </p> <p> <p>Note:  Unless you use an <span class="filepath"> .xsl </span> template when generating your reports, all reports are distributed by email as attachments. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

