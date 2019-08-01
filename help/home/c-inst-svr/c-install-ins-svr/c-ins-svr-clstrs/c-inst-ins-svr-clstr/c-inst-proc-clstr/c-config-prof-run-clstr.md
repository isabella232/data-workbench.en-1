---
description: When you configure a dataset profile to run on an Insight Server cluster, all of the machines in the cluster share all of the dataset configuration files for that profile.
seo-description: When you configure a dataset profile to run on an Insight Server cluster, all of the machines in the cluster share all of the dataset configuration files for that profile.
seo-title: Configuring a Profile to Run on a Cluster
solution: Insight
title: Configuring a Profile to Run on a Cluster
uuid: b6cad562-47b9-4a38-b810-c5f342c84e8f
index: y
internal: n
snippet: y
---

# Configuring a Profile to Run on a Cluster{#configuring-a-profile-to-run-on-a-cluster}

When you configure a dataset profile to run on an Insight Server cluster, all of the machines in the cluster share all of the dataset configuration files for that profile.

 Therefore, the entries for the parameters in these files must be applicable to all [!DNL Insight Servers] in the cluster. For example, the locations of the log files to be read, the lookup files to be used by [!DNL Insight Server], and the location of the data output by [!DNL Insight Server] must be the same on all machines in the cluster.

You perform all configuration tasks on the cluster’s master [!DNL Insight Server], which is the [!DNL Insight Server] you use to edit your configuration files. All saved configuration file changes made on the master [!DNL Insight Server] are synchronized automatically to the files on the processing [!DNL Insight Servers] in the cluster.

To run a dataset profile on an [!DNL Insight Server] cluster, you must perform the following processes in the order listed:

1. [Determining Which Insight Servers Process Event Data](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba) 
1. [Specifying the Processing Servers in Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9) 
1. (If necessary) [Modifying the Dataset Configuration Files for the Profile](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determining Which Insight Servers Process Event Data {#section-59b8e3f2b34f49739d544c8740a62fba}

It is not required that all [!DNL Insight Servers] in the cluster process event data. You can designate one [!DNL Insight Server] in the cluster as a File Server Unit that stores the source files (VSL and log files) and serves the files to all of the Data Processing Units (processing servers) in the cluster. This setup provides the benefit of a single event data repository and leverages the processing power of all the processing servers in the cluster. The processing servers divide the data files among them and guarantee that the same file is not processed more than once.

For more information about designating an [!DNL Insight Server] to run as a File Server Unit, see the Log Processing Configuration File chapter of the *Dataset Configuration Guide*.

If you decide to store source data files on each of the processing servers rather than on a single File Server Unit, you must divide the files equally among the processing servers. Do not store all of the dataset’s source files on each of the processing servers. If multiple copies of the same file are available to multiple processing servers, the data is read multiple times (once by each machine) and skews your data.

For help determining which [!DNL Insight Servers] should process log files, please contact Adobe Consulting.

## Specifying the Processing Servers in Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

In the [!DNL profile.cfg] file, specify the processing servers that process the data for the profile.

**To access the profile.cfg file**

You access the profile configuration file using the [!DNL Profile Manager] in [!DNL Insight].

1. While working in your dataset profile, open the [!DNL Profile Manager] by right-clicking within a workspace and clicking **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**, or by opening the Profile Management workspace on the [!DNL Admin] tab. 

1. In the [!DNL Profile Manager], right-click the check mark next to [!DNL profile.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 

1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. The profile configuration window appears.

**To add the Processing Servers**

1. In the [!DNL profile.cfg] file, click **[!UICONTROL Profile]**, then click **[!UICONTROL Processing Servers]** to display its contents. 

1. Right-click **[!UICONTROL Processing Servers]** and click **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**. 

1. In the Common Name parameter, type the common name for the first processing server in the cluster. For example: [!DNL server1.mycompany.com]
1. Repeat Steps 2 and 3 until you have added the common names of all of the processing servers in the cluster.

   >[!NOTE]
   >
   >If the master [!DNL Insight Server] processes data, you must add it as well.

1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 

1. Right-click the check mark in the [!DNL User] column next to [!DNL profile.cfg]. Click **[!UICONTROL Save to]** > *< **[!UICONTROL dataset profile name]**>*.

## Modifying the Dataset Configuration Files for the Profile {#section-99bf9248e4e5483cb518f453b0a2f278}

**To modify the dataset configuration files**

If you need to make changes to the dataset configuration files ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], dataset include files, [!DNL Log Processing Mode.cfg], and so forth), do so only on the master [!DNL Insight Server].

1. Access the files you want to modify:

   For instructions to access the files, see the *Dataset Configuration Guide*. 
1. Make your changes. See the *Dataset Configuration Guide* for details regarding the parameters within the configuration file(s). 
1. Save the file.

    1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 
    
    1. Right-click the check mark in the [!DNL User] column next to the file name. 
    1. Click **[!UICONTROL Save to]** and select the desired profile.

>[!NOTE]
>
>[!DNL Insight] users who access a dataset profile running on a cluster identify only the master [!DNL Insight Server] in the [!DNL Insight] configuration file ( [!DNL insight.cfg]). From the perspective of the [!DNL Insight] user, the profile is accessible on only one [!DNL Insight Server] (the master [!DNL Insight Server]); however, query requests from analysts can be directed to any of the [!DNL Insight Servers] in the cluster.

An [!DNL Insight Server] cluster permits the centralized storage of [!DNL .vsl] log files (from [!DNL Sensor]) on a single [!DNL Insight Server] machine called a File Server Unit (FSU). For information about installing an FSU, see [Installation Procedures for an Insight Server FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). For information about configuring an FSU, see the *Dataset Configuration Guide*. 
