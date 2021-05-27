---
description: If network firewalls do not prevent access to the repeater server from Insight machines, you can create a connection between the repeater server and Insight so that you can manage the repeater server using Insight.
title: Creating a Connection Between Insight and Repeater
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
---
# Creating a Connection Between Insight and Repeater{#creating-a-connection-between-insight-and-repeater}

If network firewalls do not prevent access to the repeater server from Insight machines, you can create a connection between the repeater server and Insight so that you can manage the repeater server using Insight.

 **To create a connection between [!DNL Insight] and the repeater server** 

1. In [!DNL Insight], on the [!DNL Admin] tab, click the **[!UICONTROL Configure Connections to Servers]** thumbnail to open the Configure Connections to Servers workspace.
1. In the [!DNL Insight.cfg] window, right-click **[!UICONTROL Servers]** and click **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. For the new server, complete the following parameters:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Specify... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2">(Optional) The name that you want this <span class="keyword"> Insight</span> to use to represent the repeater server in its user interface. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <p>The host name or numeric IP address of your repeater server. </p> <p>Example: <span class="filepath"> Repeater.mycompany.com</span> or 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <p>Optional unless you have more than one certificate. The name of the file that contains the digital certificate for this copy of <span class="keyword"> Insight</span>. (This is the file that you downloaded while installing <span class="keyword"> Insight</span>.) </p> <p>Example: <span class="filepath"> Samantha Smith.pem</span></p> <p>If you leave this parameter blank, <span class="keyword"> Insight</span> uses whatever certificate is present. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Server </p> <p>Common Name </p> </td> 
   <td colname="col2">The common name assigned to the repeater server. This name must match the common name assigned to the repeater server within its license certificate. If you have access to the repeater’s certificate file (<span class="filepath"> Certificates\server_cert.pem</span>), you can find the common name by opening the file with a text editor such as Notepad. The common name is identified in the CN field in the certificate. </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**. [!DNL Insight] will attempt to connect to the repeater server using the settings you have specified. If a connection is established, a green server icon appears in the [!DNL Servers Manager] interface. If a connection cannot be established, a red icon appears.

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.
