---
description: Open functionality enables you to open such items as documents or URIs in such external applications as a text editor or a web browser.
solution: Analytics
title: Configure open functionality
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
---
# Configure open functionality{#configure-open-functionality}

Open functionality enables you to open such items as documents or URIs in such external applications as a text editor or a web browser.

Open functionality is currently configured only in the [!DNL Site] application and only for opening URIs. This section provides information about configuring Open URI functionality for [!DNL Site]. For information about configuring Open functionality for another application or to open other items, contact Adobe Consulting Services.

In [!DNL Site], you can right-click a URI from a page overlay or table to display the URI in the application for which it was formatted. For example, from a URI table visualization, you can click a URI to display a web page in a web browser.

To open a URI from a visualization, you first must edit the [!DNL Open URI.cfg] file for the URI dimension to identify the location and naming conventions that Data Workbench uses to open the URI. To view a URI in its native format (such as HTML), Data Workbench must have access to the referenced location and the application needed to open that item. For example, to view a web page, Data Workbench would need access to the Internet as well as have a web browser installed.

**To edit Open URI.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**. 
1. In the URI folder, right-click the check mark next to the [!DNL Open URI.vw]file and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]** if the file is a [!DNL .cfg] file or **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** if it is a [!DNL .vw] file. 
1. Click **[!UICONTROL Command]**, then **[!UICONTROL Parameters]** to view the contents of the file. 
1. Modify the [!DNL Site] parameter and the Template parameter as necessary:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Provide this information... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Site </p> </td> 
   <td colname="col2"> <p>The location of the URIs that you want to open. </p> <p>Example: mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Template </p> </td> 
   <td colname="col2"> <p>The parameters that Data Workbench should use to locate and open the URIs. </p> <p>Example: <span class="filepath"> http://%Site%%URI%</span> </p> <p>The default template shown in the example tells Data Workbench to open a web browser, look for the location defined in the <span class="wintitle"> Site</span> parameter, then locate the URI dimension element you are attempting to open. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file. 
1. To make this change available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
