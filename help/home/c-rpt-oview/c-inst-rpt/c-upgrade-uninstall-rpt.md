---
description: Information about upgrading and uninstalling your Report Server software.
seo-description: Information about upgrading and uninstalling your Report Server software.
seo-title: Upgrading and Uninstalling Report Server
solution: Analytics
title: Upgrading and Uninstalling Report Server
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
---

# Upgrading and Uninstalling Report Server{#upgrading-and-uninstalling-report-server}

Information about upgrading and uninstalling your Report Server software.

* [Upgrading Report](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282) 
* [Uninstalling Report](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Upgrading Report Server {#section-95fea4bddad74616a8aea450dcdb2282}

If you are upgrading to [!DNL Report Server] 5.4, you can use the instructions to upgrade your [!DNL Report Server] software. If you are using [!DNL Report Server] 3.6 or earlier, contact Adobe for assistance with your upgrade.

To upgrade [!DNL Report Server] 5.4, use data workbench to copy an upgrade file to the data workbench server to which [!DNL Report Server] connects. After doing so, [!DNL Report] Server instances automatically upgrade themselves when they connect to that server and load a profile.

>[!NOTE]
>
>Before upgrading [!DNL Report Server], make sure that you have properly upgraded your data workbench server software as well as the profiles running on the data workbench server. For more information, contact Adobe Consulting Services.

To perform the following procedure, you first must obtain the upgrade file for [!DNL Report Server].

**To upgrade to [!DNL Report Server] 5.4 and later versions**

1. Make a backup of all of the files under [!DNL E:\Portal] and remove all files and folders within this directory. 
1. Copy the contents of the new build into [!DNL E:\Portal]. 
1. Modify [!DNL global.asa], [!DNL email.asp], and [!DNL TopNavigation.xml] as per the instructions in the previous section. 

1. Copy the [!DNL users.mdb] from your backup.

   >[!NOTE]
   >
   >If you did not previously generate reports with a .png ouput, you need to go into the individual report folders and modify the [!DNL reports.xml] to include a report format of png. Otherwise you may get a 500 error. Your original [!DNL reports.xml] would look something like the following:

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   It would need to be modified to the following:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. In the [!DNL report.cfg], include an output format of png and save. Going forward, it should generate reports in png format.

**To upgrade to [!DNL Report Server] 4.0**

1. On the data workbench computer, copy the Report Server upgrade file to the [!DNL Temp\Software] folder in the directory where data workbench is installed. 
1. Start data workbench and load the [!DNL Configuration] profile. 
1. Click the **[!UICONTROL Configure Connection to Servers]** thumbnail. 
1. In the [!DNL Servers Manager], right-click the data workbench server icon and click **[!UICONTROL Server Files]**. 

1. In the Software folder, open the [!DNL Report Server] folder. 
1. Right-click the **[!UICONTROL Temp]** check mark for [!DNL ReportServer.exe] and select **[!UICONTROL Save to]** > *< **[!UICONTROL server name]**>*.

## Uninstalling Report Server {#section-96eb3281c45a45c0a7065deaa6845c25}

**To uninstall [!DNL Report Server]**

1. Unregister the [!DNL Report Windows] service.

    1. Open a command prompt and navigate to the bin sub-directory in the folder where you installed the data workbench server (InsightServer64.exe.) Example: [!DNL D:\Adobe\Report\bin] 
    1. At the command prompt, execute the following command to stop and unregister it as a service under Microsoft Windows: [!DNL visualreport /unregserver]

1. Delete the Report Server installation directory.

