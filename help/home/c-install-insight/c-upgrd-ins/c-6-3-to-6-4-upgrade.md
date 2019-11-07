---
description: Follow these steps to upgrade to Data Workbench v6.4.
title: Upgrading 6.3 to 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
---

# Upgrading 6.3 to 6.4{#upgrading-to}

Follow these steps to upgrade to Data Workbench v6.4.

## Upgrade Requirements and Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Follow these requirements and recommendations when upgrading to Data Workbench 6.4.

>[!IMPORTANT]
>
>It is recommended that you use the newly installed default configuration files and customize them, rather than moving files from a previous installation—with these exceptions:

* **Add** ***Excluded Processes*** for *MS System Center Endpoint Protection in Windows 2012 Servers* for the following executables:

    * **[!DNL InsightServer64.exe]** 
    * **[!DNL ReportServer.exe]** 
    * **[!DNL ExportIntegration.exe]**

  This will allow "white list" rights for these interfacing executables. 

* **Update the *Trust_ca_cert.pem* certificate on the servers**. 
* **Reorganization of Attribution Profiles**.

    * The *Attribution* folder was renamed to ***Attribution - Premium*** (found in the default installation at *Profiles*\*Attribution - Premium*). 
    
    * The *Premium* profile was removed and the workspace moved to the new ***Attribution - Premium*** folder.

* **Update *Attribution-Premium* settings**. If you have customized profiles with parameter settings that override the default *Adobe SC* profile, then you need to update the custom fields in these configuration files:

    * **[!DNL Decoding Instructions.cfg]** 
    * **[!DNL SC Fields.cfg]**

* Because of this reorganization, you will want to remove the old *Attribution* and *Premium* folders from your server installation.

  **Change these settings** 

  ```
  Profile = profileInfo:  
    Active = bool: true 
    Directories = vector: 6 items 
      0 = string: Base\\ 
      1 = string: Geography\\ 
      2 = string: Predictive Analytics\\ 
      3 = string: Adobe SC\\ 
       
<b>4 = string: Attribution\\ 
       5 = string: Premium\\</b>
  ```

  to these settings:

  ```
  Profile = profileInfo:  
    Active = bool: true 
    Directories = vector: 5 items 
      0 = string: Base\\ 
      1 = string: Geography\\ 
      2 = string: Predictive Analytics\\ 
      3 = string: Adobe SC\\ 
       
<b>4 = string: Attribution - Premium\\</b>
  ```

* **Update custom Meta.cfg files** (if necessary).

  The **[!DNL Meta.cfg]** files in **[!DNL Base\Context and AdobeSC\Context]** folders have been updated in this release.

  If you override the **meta.cfg** file during installation, then your profile copy needs to be updated with this these parameters and the **metadata vector** appropriately entered:

  ```
  94 = meta: 
    path = string: SegmentExport:CRS Configuration/CRS Attributes 
    acceptable children = vector: 1 items 
      0 = Template: 
        name = string: CRS Attributes 
        value = CRSAttributeConfiguration: 
          Attribute Name = string: 
          Attribute Type(int,string) = string: 
          Field Name = string: 
           
  95 = meta: 
    path = string: SegmentExportQuery:CRS Configuration/Report Suite 
    acceptable children = vector: 1 items 
      0 = Template 
        name = string: Add Report Suite 
        value = string:
  ```

* **Set Report Server permissions** to generate Microsoft Excel reports On Windows 2012 servers.

    1. Set permission of the root folder (**[!DNL E:\ReportServer\]**) to *Everyone = full control*. 
    
    1. Create the following folders with appropriate permissions:     
    
       ```    
       C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
       C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
       C:\Windows\System32\config\systemprofile\Desktop 
       C:\Windows\SysWOW64\config\systemprofile\Desktop
       ```

       >[!NOTE]
       >
       >If you are running Report Server on Windows Server 2012, you need to have Windows Server 2012 R2 installed.

    1. Assign "SYSTEM" as the owner for these folders.

* **Add fonts to the Report Server.** In the **[!DNL ReportServer.cfg]**file, add these fonts (for all languages): 

  ```
  Fonts = vector: 3 items 
    0 = string: Arial 
    1 = string: SimSun 
    2 = string: MS Mincho
  ```

* **Update your version of Microsoft Excel **(if necessary).

  With the release of Data Workbench 6.4, support for Excel 2007 has been discontinued. Also because Data Workbench only runs on Microsoft Windows for 64-bit architecture, it is recommended that you also install a 64-bit version of Microsoft Excel. 

* **64-bit architecture** required for Workstation (Client) installation. 
* **Run the Workstation Setup Wizard**.

  Install the new version of the workstation (client) by downloading and launching ***InsightSetup.exe*** and stepping through the setup instructions. The setup wizard will install your files to a new location by default:

  Program files are now saved by default to: 

  ```
  C:\Program Files\Adobe\Adobe Analytics\Data Workbench
  ```

  Data Files (profiles, certificates, trace logs, and user files) are now saved by default to: 

  ```
  C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
  ```

* **Add fonts to the Workstation**.

  In the **[!DNL Insight.cfg]** file, add these fonts (for all languages):

  ```
  Fonts = vector: 3 items 
    0 = string: Arial 
    1 = string: SimSun 
    2 = string: MS Mincho
  ```

