---
description: Steps to map the Report Portal to a virtual directory (IIS 7.0 or higher).
title: Mapping Report Portal to a Virtual Directory (IIS 7.0 or higher)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
---
# Mapping Report Portal to a Virtual Directory (IIS 7.0 or higher){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Steps to map the Report Portal to a virtual directory (IIS 7.0 or higher).

Currently, most Managed Service clients have servers with the Windows Server 2008 operating system and the IIS 7.0 or higher web server.

## Prerequisites {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Make sure that ASP and [!DNL ASP.Net] components are installed for IIS 7.0 or higher. 
* Make sure the IIS Web user has [!DNL Modify] access to the [!DNL E:\Portal\data\users.mdb] file. You can change that by right-clicking on the **[!UICONTROL users.mdb]** file and under [!DNL Properties], go to the [!DNL Security] tab. If you do not see the IIS Web User listed or do not have the ability to add the IIS Web User to the list, simply give the [!DNL Users] group the [!DNL Modify] access. 

* Make sure whatever user account is being used to run the [!DNL Application Pools] also has [!DNL Modify] access to the [!DNL E:\Portal\data\users.mdb] and the [!DNL C:\Windows\Temp\] folders.

## Installation Steps {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. On the machine where [!DNL Report Portal] is installed, start the [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**. 

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**. 

1. Right-click **[!UICONTROL Default Web Site]** and select **[!UICONTROL Add Virtual Directory]**. 

1. For an alias, enter Portal. 
1. For the physical path, enter [!DNL E:\Portal\PortalASP]. 
1. Click **[!UICONTROL OK]**.

   The virtual directory that you created appears under the [!DNL Default Web Site]. 

1. Add the following virtual directories under the virtual directory that you just created. 

   |  Create this alias...  | For this physical resource  |
   |---|---|
   |  Core  | [!DNL E:\Portal\PortalFiles\Core]  |
   |  CSS  | [!DNL E:\Portal\PortalFiles\CSS]  |
   |  Images  | [!DNL E:\Portal\PortalFiles\Images]  |
   |  Output  |Physical location of the directory in which [!DNL Report Server] saves the output for your report sets. The output folder can be located anywhere and can be named anything. It contains a subfolder for each report set. You can delete the [!DNL E:\Portal\PortalFiles\Output], but move the [!DNL profiles.xml] to the physical location of the Output file.  |

1. When finished, verify that IIS displays four new virtual directories. Make sure that the directory structure has one parent folder (with the same name as your portal) and four subfolders. 
1. Click on **[!UICONTROL Application Pools]**, then **[!UICONTROL DefaultAppPool]** (assuming that's the one you set up with your portal). 

1. Click on **[!UICONTROL Advanced Settings]** and select True for the Enable 32-Bit Applications. 
1. To get the [!DNL Portal] to work, you need to convert it to an application. After setting up the virtual directories, right click on the Portal virtual directory and select **[!UICONTROL Convert to Application]**.

## Additional Tips and Tricks {#section-ff84ab3f66c94620a6a11f0e60471d44}

* You can download the [!DNL Portal] from Softdocs under **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. You can simply download the [!DNL ReportPortal-Release-1-0-0-7.zip]. 

* You no longer need the [!DNL ReportPortalSetup.xml], so it can be deleted. 
* For the sake of standardization, place the contents of this zip file into [!DNL E:\Portal]. 
* To determine the SMTP server For managed services clients, you can go look here. 
* Put in a request with NetOps to change the domain name entry in IIS for the report server to something friendlier - for example, [!DNL reports.clientname.insight.omniture.com], so that your overall portal URL is [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configure your [!DNL email.asa] file once this change has been put into place.
