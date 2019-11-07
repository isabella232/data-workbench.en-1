---
description: The following are requirements and recommendations for installing the Workstation (Client) in Data Workbench.
solution: Analytics
title: Workstation requirements
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
---

# Workstation requirements{#workstation-requirements}

The following are requirements and recommendations for installing the Workstation (Client) in Data Workbench.

 See [server system requirements](http://marketing.adobe.com/resources/help/en_US/insight/svrprod/index.html#Server_System_Requirements) for additional Data Workbench system requirements.

>[!IMPORTANT]
>
>The server, report server, and client components are upgraded to run on 64-bit Windows operating systems.

**Before You Begin**

Make sure you have the these tasks completed before installing the Data Workbench Workstation (Client):

* **Add** ***Excluded Processes*** for *MS System Center Endpoint Protection in Windows 2012 Servers* for the following executables:

    * **[!DNL InsightServer64.exe]** 
    * **[!DNL ReportServer.exe]** 
    * **[!DNL ExportIntegration.exe]**

  This will allow "white list" rights for these interfacing executables. 

* **Install Microsoft Excel to export analysis data.** To export data from workspaces as Microsoft Excel ( [!DNL .xls] or [!DNL .xlsx]) files, the computer on which you install Data Workbench must have Excel installed and registered. If Excel has not been registered and Data Workbench tries to access it for the first time, Excel displays a registration dialog box. If you are not sure whether the copy is registered, start Excel manually, and if a registration dialog box appears, complete the registration process. 

  >[!NOTE]
  >
  >With the release of Data Workbench 6.4, support for Excel 2007 has been discontinued. Also, because Data Workbench only runs on Microsoft Windows for 64-bit architecture, it is recommended that you also install a 64-bit version of Microsoft Excel.

* **Installing Adobe [!DNL Acrobat] for printing scaled workspaces to PDF.** To print scaled workspaces to Adobe PDF format, the computer on which you installed Data Workbench must have Adobe [!DNL Acrobat] installed. 

* **Providing access to a printer for printing workspaces.** To print workspaces from Data Workbench, the computer on which you install Data Workbench must have access to a printer. Data Workbench can print workspaces to color or monochrome printers and does not require postscript or other advanced printer features. For optimal results, Adobe recommends printing workspaces in color. 
* **Implement security measures.** You should follow your company’s normal enterprise security policies for Data Workbench computers. To serve its primary purposes, Data Workbench requires only the ability to connect to a server (via ports 80 and 443) and to any servers collecting data. You can use the Data Workbench hardware for any other purpose as long you maintain the Data Workbench software and allocate at least 10 GB of storage space for Data Workbench. 
* To render visualizations accurately, the computer on which you install the workbench must have an appropriate **graphics adapter **installed (see Graphic Adapter requirements below).

**Data Workbench Client Requirements**

**Operating System**

* Microsoft Windows 7 64-bit 
* Microsoft Windows 8.1 64-bit 
* Microsoft Windows 10 64 bit

>[!NOTE]
>
>Windows XP is not supported for Data Workbench 6.1 and later versions.

**Resolution**

* Required: 1024 x 768 (XGA) 
* Recommended: 1920 x 1200 (WUXGA)

**Graphics Adapter**

* Required: OpenGL hardware acceleration to support OpenGL 3.2 
* Recommended: Dedicated video adapter (e.g., NVIDIA or ATI adapter)

**Processor**

* Required: 1.2 GHz or higher Intel or AMD 
* Recommended: ICore 2 Duo-Class

**RAM**

* Required: 2 GB 
* Recommended: 4 GB

**Connectivity**

* Required: 512 Kbps link to the DPU 
* Recommended: 2Mbps or faster link to the DPU

**File System**

NTFS

**Disk Storage**

At least ten (10) GB or greater of free hard disk drive space

**Printing**

Printer access (color or gray scale printers) for printing workspaces and reports

**Other**

* Dedicated mouse 
* Low-glare working environment 
* Matte-surfaced monitor

