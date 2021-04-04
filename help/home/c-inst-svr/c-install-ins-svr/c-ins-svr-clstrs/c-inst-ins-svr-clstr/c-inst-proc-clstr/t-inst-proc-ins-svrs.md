---
description: A processing Insight Server is identical to a master Insight Server except for the contents of its Components directory.
solution: Analytics
title: Installing and Configuring the Processing Insight Servers
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
---
# Installing and Configuring the Processing Insight Servers{#installing-and-configuring-the-processing-insight-servers}

A processing Insight Server is identical to a master Insight Server except for the contents of its Components directory.

 The Components directory on a processing [!DNL Insight Server] contains a special set of files that are specifically configured for processing [!DNL Insight Servers]. These files are derived from the Components for Processing Servers directory on the master [!DNL Insight Server].

When you install a processing [!DNL Insight Server], you do the following to set up its Components directory:

1. Delete the original Components directory on the processing [!DNL Insight Server]. 
1. Rename the Components for Processing Servers directory to Components. 
1. Modify the [!DNL Synchronize.cfg] in the Components directory to point to the master [!DNL Insight Server].

**To install and configure a processing [!DNL Insight Server]** 

1. Install the [!DNL Insight Server] program files as described in [Installing the Insight Server Program Files](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Be sure to duplicate the directory structure that was used on the master [!DNL Insight Server]. For example, if [!DNL Insight Server] is installed in [!DNL C:\Adobe\Server] on the master [!DNL Insight Server], you must install it in [!DNL C:\Adobe\Server] on the processing [!DNL Insight Servers] as well.
1. Install the digital certificate that Adobe has issued for this particular processing [!DNL Insight Server]. See [Downloading and Installing the Digital Certificates](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) for instructions.
1. Using Windows Explorer, do the following on the processing [!DNL Insight Server]:

    1. Delete the **[!UICONTROL Components]** folder. 
    1. Rename the [!DNL Components for Processing Servers] folder to Components.

1. Using a text editor such as Notepad, open the [!DNL Synchronize.cfg] file in the Components directory on the processing [!DNL Insight Server].
1. Add the IP address of the master (primary) [!DNL Insight Server] to the second line of this file as shown in the following file fragment. Do not edit anything else in this file.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Save the file.
1. Start the [!DNL Insight Server] as described in [Registering Insight Server as a Windows Service](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   You have now completed the installation of your [!DNL Insight Server] cluster. Next, configure the dataset profile to run on the cluster as described in the following section.
