---
description: Access to and permissions within your Report Portal are controlled using individual user and group accounts.
seo-description: Access to and permissions within your Report Portal are controlled using individual user and group accounts.
seo-title: Edit the Email.asp File
solution: Analytics
title: Edit the Email.asp File
topic: Data workbench
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
---

# Edit the Email.asp File{#edit-the-email-asp-file}

Access to and permissions within your Report Portal are controlled using individual user and group accounts.

 Each time that you add a new account or edit an existing account, a confirmation email can be sent to the email address that you specify for that account (see [Working with Accounts](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) and copied to the email addresses that you specify in the [!DNL email.asp] file.

>[!NOTE]
>
>Notification emails are sent to account users only when you have specified an email address for the account and properly configured the [!DNL email.asp] file. If you do not want notification emails sent for an account, leave the account’s email field blank.

This file resides in the `\*PortalName*\PortalASP` folder. 

1. On the machine where IIS is running, open the [!DNL email.asp] file in a text editor such as Notepad.
1. Set the following variables:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> For this variable . . . </th> 
   <th colname="col2" class="entry"> Provide this information . . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>DNS name or IP address of the SMTP server through which messages are sent. </p> <p>For example: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> The port on which the SMTP server listens for connections. This is typically port 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sendusing </td> 
   <td colname="col2"> <p>Indicates how the message is to be sent. Values are: </p> <p>1 - Send messages using the locally installed SMTP service. Use this value if the SMTP service is installed on the computer where the script is running. </p> <p>2 - Send messages using the SMTP service on the network. Use this value if the SMTP service is not installed on the computer where the script is running. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">The amount of time that <span class="wintitle"> Report</span> should wait for a response from the SMTP server before it times out the connection. </td> 
  </tr> 
 </tbody> 
</table>

1. For the [!DNL NewUserEmail()] and [!DNL UpdateUserEmail()] functions, set the following variables:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> For this variable . . . </th> 
      <th colname="col2" class="entry"> Provide this information . . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> From </td> 
      <td colname="col2">The text that you want to appear in the From header line in your confirmation emails. This value might be the same as the <span class="wintitle"> CC</span> value. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Optional. The valid email address of the person or alias who should receive a copy of all messages regarding new and changed user accounts. You can specify multiple email addresses by separating the addresses with commas (no spaces). </p> <p>For example: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Note:  The recipients receive copies of emails that contain user passwords. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Subject </td> 
      <td colname="col2"> The text that you want to appear in the Subject header line in your confirmation emails. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>The actual path to your portal. </p> <p>For example: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Body </td> 
      <td colname="col2"> <p>The text included in the automatically generated emails. </p> <p>For example, following is the default text included in the emails sent to provide login information: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Your web portal login information is provided below: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName: username </p><p>New Password: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>You may access the portal using the following URL: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">After you log into the portal, you can change your password on the <span class="wintitle"> Admin</span> tab. </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Save and close the file.
