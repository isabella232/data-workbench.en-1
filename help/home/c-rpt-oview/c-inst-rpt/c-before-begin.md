---
description: For some of the features of Report Server to work, you must provide and configure hardware or software before installing.
title: Before You Begin
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
---
# Before You Begin{#before-you-begin}

For some of the features of Report Server to work, you must provide and configure hardware or software before installing.

## Basic Report Server Requirements {#section-e891eaee79fe4fa98e658426dc3b2777}

The reports that are output can either be in the form of .PNG images or .XLS spreadsheets placed in a file system, or as emails. Hardware requirements are identical to the [data workbench client](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

The following requirements exist for Report Server:

* Access to file system for output of data (network share, or local drive). 
* Access to configured SMTP server. 
* Microsoft Excel 2010 64-bit or above installed on [!DNL Report] Server. See [Considerations for server-side Automation of Office](http://support.microsoft.com/kb/257757) for additional information.

## Additional Requirements {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Install an Appropriate Graphics Adapter.** To properly render reports, the machine on which you install [!DNL Report] Server must have an appropriate graphics adapter installed. 

* **Install Microsoft Excel to Generate Reports as Excel Files.** To generate and distribute reports as Microsoft Excel files ( [!DNL .xls] or [!DNL .xlsx]), the machine on which you install Report Server must have the appropriate version of 64-bit Microsoft Excel installed and registered. If Excel has not been registered and Report Server tries to access it for the first time, Excel will display a registration dialog box. If you are not sure whether the copy is registered, start Excel manually and if a registration dialog box appears, complete the registration process.

  >[!NOTE]
  >
  >When you generate reports as Excel files, you are opening a new instance of Excel. For more information about this process, see [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Provide access to an SMTP server to distribute reports by email.** If you would like to distribute reports in email, Report Server must be able to connect to an SMTP server, and the appropriate ports to the email forwarding service must be opened.
