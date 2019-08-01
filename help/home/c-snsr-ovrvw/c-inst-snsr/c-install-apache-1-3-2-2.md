---
description: Instructions for installing and configuring Sensor for Apache Server 1.3, Apache Server 2.0.42 or later, or Apache Server 2.2 running under Microsoft Windows Server 2000 or later.
seo-description: Instructions for installing and configuring Sensor for Apache Server 1.3, Apache Server 2.0.42 or later, or Apache Server 2.2 running under Microsoft Windows Server 2000 or later.
seo-title: Apache Server 1.3, 2, 2.2, or 2.4 on Windows Server 2000 or Later
title: Apache Server 1.3, 2, 2.2, or 2.4 on Windows Server 2000 or Later
uuid: 553790b6-4178-4ff8-aa8e-fbf600774367
index: y
internal: n
snippet: y
---

# Apache Server 1.3, 2, 2.2, or 2.4 on Windows Server 2000 or Later{#apache-server-or-on-windows-server-or-later}

Instructions for installing and configuring Sensor for Apache Server 1.3, Apache Server 2.0.42 or later, or Apache Server 2.2 running under Microsoft Windows Server 2000 or later.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

* Apache Server 1.3 
* Apache Server 2.0.42 or later 
* Apache Server 2.2 running under Microsoft Windows Server 2000 or later

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Before installing the program files, you must determine where you want to maintain the disk queue because that is also where you must install the program files.Procedure to extract and install the program files for Sensor.

To install and configure Sensor, you must perform the following steps:

1. On your Windows machine, create a directory in which to install the Sensor program files. Keep in mind that your disk queue also resides in this directory, so be sure the device you choose has sufficient space to hold a queue of the size you need. 

   ```
   C:\VisualSensor
   ```

1. Extract the contents of the installation file into the directory you just created. During this step, Sensor installs the following files:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Event Viewer messages. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> The collector module. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>An Excel spreadsheet file that architects can use to configure a controlled experiment. Sensor does not use this file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> The certificate used to validate the digital certificate that Insight Server presents during the connection process. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> The transmitter program </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> The Sensor configuration file </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The installation package contains a spreadsheet file called TestExperiment.xls. This spreadsheet is a tool that architects use to configure a controlled experiment. Sensor itself does not use this file, so it is not necessary to install the file on the machine where Sensor is running (although you can choose to do so). You might want to, instead, copy the file to a location where your architects can access it or simply extract the file from the installation package as needed. For more information about controlled experimentation, see the Insight Controlled Experiments Guide.

****

## Edit the Sensor Configuration File {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

The [!DNL txlogd.conf] file contains the configuration parameters for Sensor.

You must edit this file to specify, among other things, the size and location of the disk queue file, the address of the Insight Server, and the ID that will be attached to the event data produced by this sensor.

The configuration file contains required parameters and optional parameters.

* **Required parameters** are settings that you must specify when you install Sensor. Without these settings, Sensor does not run successfully. 
* **Optional parameters** are settings that default to pre-defined values (which you can modify) or enable optional features.

**To edit the Sensor configuration file**

* Open the [!DNL /etc/txlogd.conf] file in a text editor and set the required parameters as well as any desired optional parameters. 
* Save and close the file.

**To edit the Sensor configuration file**

1. Open the [!DNL /etc/txlogd.conf] file in a text editor and set the required parameters as well as any desired optional parameters. 
1. Save and close the file.

## Start the Transmitter and Create the Disk Queue {#section-55630de65f264274aefd771da2002852}

After you configure the txlogd.conf file, you can start the transmitter program, register it as a Windows service, and create the disk queue.

1. If the directory in which the disk queue resides does not already exist, create it. Make sure that the directory provides both the collector module and the transmitter program with read/write access to the file.

   For more information about the permissions required by the disk queue files, see Sensor UNIX File Permissions. 
1. On the computer where Sensor is installed, execute the following command to start the transmitter:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

    * The “i” option in this command starts the transmitter in “interactive mode.” This mode displays transmitter messages on the screen and also enables you to interact with the transmitter using keyboard commands. 
    * The “c” option directs the transmitter to create the disk queue. 
    * The “f” option specifies the location of the configuration file.

   For additional information about the options you can use when starting the transmitter, see Sensor Transmitter Command-Line Options. 

1. Verify that the transmitter has created the disk queue in the location specified in the QueueFile parameter and of the size specified in the QueueSize parameter. 
1. f the queue has not been created correctly, type Ctrl+C to terminate the transmitter, then do the following:

    1. Examine the txtlogd.conf file and verify that the QueueFile and QueueSize parameters are set correctly. 
    1. Check that the device to which the disk queue is assigned is operational and has sufficient space available to hold a file of the size specified in the QueueSize parameter. 
    1. Make any necessary corrections and repeat this procedure.

## Add the Collector to the Web Server {#section-c5b83ae4ebce430aa764f951e849b333}

For Apache servers, the collector is a dynamic shared object that you load into your web server process.

To add the collector to your web server, you must edit the [!DNL httpd.conf] file as described below and restart your web server.

>[!NOTE]
>
>If Sensor is capturing data for multiple web servers on the server computer, you must perform the following procedure for each web server.

1. Using a text editor, open the [!DNL httpd.conf]file for the web server whose events Sensor captures. 
1. Add the following two lines to the end of the file: 

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >These lines are case sensitive. Type them exactly as they appear above.

1. Restart the web server process (you do not have to reboot the entire server computer, simply restart the web server process). The collector is loaded with the web server and begins collecting event data and writing it to the disk queue.

