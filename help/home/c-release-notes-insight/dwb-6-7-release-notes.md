---
description: New features, fixes, and known issues in Data Workbench 6.7.
seo-description: New features, fixes, and known issues in Data Workbench 6.7.
seo-title: Data Workbench 6.7 Release Notes
title: Data Workbench 6.7 Release Notes
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
---

# Data Workbench 6.7 Release Notes{#data-workbench-release-notes}

New features, fixes, and known issues in Data Workbench 6.7.

## Data Workbench 6.7 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad}

New features, fixes, and known issues in Data Workbench 6.7.

## New Features in Release 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**New authentication model for Data Workbench Workstation (IMS integration)**

Data Workbench Workstation now supports user authentication through username and password. With this new method, administrators can create and manage their own user accounts, eliminating the need to contact Customer Care.

For more information, see [Self-Provisioning of Users](https://marketing.adobe.com/resources/help/en_US/insight/client/c_self-provisioning-users.html).

**Flat file lookup**

Data Workbench Workstation now supports user authentication through username and password. With this new method, administrators can create and manage their own user accounts, eliminating the need to contact Customer Care.

Flat file lookup previously loaded the entire file into in-memory buffers, bloating memory usage and creating performance issues for other subsystems. The files can now be memory mapped and cached in Windows, optimizing memory usage by setting *Memory Mapped Lookup Files* to true in [!DNL MemorySettings.cfg].

For more information, see [Self-Provisioning of Users](https://marketing.adobe.com/resources/help/en_US/insight/client/c_self-provisioning-users.html).

**Memory usage**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. See [Monitoring Memory Usage](https://marketing.adobe.com/resources/help/en_US/insight/svrprod/t_mntr_mry_usg.html) for more information.

**Security ciphers**

Added support for ECDHE and DHE.

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. For more information, see [User Administration of Group Members](https://marketing.adobe.com/resources/help/en_US/insight/svrprod/dwb_self_admin_member_access.html).

**Help Menu**

Help menu now shows a shortcut to Open Certificates directory.

**`TargetBulkUpload` export**

URLs will be provided at the end of the export trace file and the `targetbulkuploadexportname.log.completed` file to track the record of stuck batches.

A new file, [!DNL TargetBulkUpload.cfg], has been provided to configure the Max Timeout interval (in minutes). The file is found in [!DNL Server\Admin\Export\].

## Fixes {#section-160baf6ea04c45a993777ee4260691ed}

* Fixed an issue where the Campaign Clickthrough dimension was showing inflated values. 
* Fixed an issue with generating excel files from the report server. 
* RC4 cipher is now disabled by default. 
* Fixed an issue causing the Data Workbench workstation to crash when adding a dimension element to a value legend table. 
* Fixed an issue with Data Workbench to AAM exports that was causing timeouts. 
* Fixed an issue causing the Data Workbench workstation to crash when a user without sufficient access level saved the workspace to Server. 
* Fixed an issue with the date format in [!DNL report.cfg] being incorrect or not localized.  
* Fixed an issue with the mobile and product rows in the AVRO feed displaying confusing information. 
* Fixed an issue that prevented the ordering of `*.1cd` and `*.1ad` files in [!DNL order.txt].  

* Submit To Server option has been disabled for Expectation Maximization algorithm while running Clustering. 
* Fixed an issue with the `TargetBulkUpload` executable stalling and failing to run completely.

## Known Issues {#section-d76322bdac5043f087ab303dc68b8fff}

* On log out, the [!DNL user cache.db] file is cleaned.  
* IMS user email addresses containing '+' or '%' characters are not supported. 
* User is unable to logout during an error in connection status. As a workaround, logout in offline mode. 
* IMS login window does not render properly on some hardware with high resolution and high DPI. As a workaround, right-click on [!DNL Insight.exe] and navigate to **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, then check the box **[!UICONTROL Override high DPI scaling behavior]**.

## Upgrade Requirements {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Update [!DNL trust_ca_cert.pem] on the Insight Servers which is part of build package. 
1. Update Server's and Report Server's certificate by downloading new certificates from [https://aap.adobe.com](https://aap.adobe.com). 
1. To automatically update Workstation and Report Server, manually update [!DNL trust_ca_cert.pem] for both by downloading it from the License Server. 
1. Sensor's automatic update feature requires version 5.0 in order to communicate with Insight Server version 6.70. Also, Sensor's [!DNL trust_ca_cert.pem] must be updated manually by downloading it from the License Server.

## System Updates {#section-c1b4949ea734440aa62658ac313261db}

New files include:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg] 
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg] 
1. [!DNL Server\Components\MemorySettings.cfg]

Updated files include:

1. [!DNL trust_ca_cert.pem] for all components. 
1. [!DNL Access Control.cfg] to support IMS configuration. 
1. [!DNL Base\Context\meta.cfg] for supporting Start Date and End Date formats in [!DNL Report.cfg] 

1. Additions to [!DNL Insight.cfg] to support proxy for IMS authentication:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   
   ```

See [archived release notes](https://marketing.adobe.com/resources/help/en_US/insight/insight_release_notes_prev.pdf) for Data Workbench 5.3 to 5.52. 
