---
description: Instructions about how to install and configure Apache Server 2.0.40, 2.0.42 or later, Apache Server 2.2, or Apache Server 2.4 on Linux, Sun Solaris, or FreeBSD.
title: Apache Server 2.0.40, 2.0.42 or later, and Apache Server 2.2 or 2.4 on Linux, Solaris, or FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
---

# Apache Server 2.0.40, 2.0.42 or later, and Apache Server 2.2 or 2.4 on Linux, Solaris, or FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

Instructions about how to install and configure Apache Server 2.0.40, 2.0.42 or later, Apache Server 2.2, or Apache Server 2.4 on Linux, Sun Solaris, or FreeBSD.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

To install and configure Sensor, you must perform the following high-level steps:

The following Apache Servers are supported:

* Apache Server 2.0.40 running under RedHat Linux 7.x or later, or Sun Solaris SPARC 2.6 or later. 
* Apache Server 2.0.40, 2.0.42 or Later, Apache Server 2.2, or Apache Server 2.4 on Linux, Sun Solaris, or FreeBSD 
* Apache Server 2.0.42 or later running under RedHat Linux 7.x or later, Sun Solaris SPARC 2.6 or later, SUSE Linux 9.x or later, or FreeBSD 5.3. 
* Apache Server 2.0.42 or later running under 64-bit versions of RedHat Linux ES 4 and ES 5. 
* Apache Server 2.2 running under RedHat Linux 7.x or later or Sun Solaris SPARC 2.6 or later. 
* Apache Server 2.4 running under RedHat Linux 7.x or later, or Sun Solaris x86_64, or FreeBSD

>[!NOTE]
>
>Although the instructions to install Sensors on web servers running Apache Server versions 2.0.40, 2.0.42 or later (32-bit and 64-bit), or 2.2 are the same (except where noted in the following procedures), the installation files for each version differ. Before installing the Sensor, ensure that you have received the correct installation files for the Apache Server and operating system versions that you are running.

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedure to extract and install the program files for Sensor.

1. Log on as the root user or as a user with root authority. 
1. Decompress and unpack the installation file using the following command:

    * On Linux:     
    
      ```    
      tar -zxf installationFilename
      ```

      ```    
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

    * On Solaris:

1. Copy the unpacked program files to the directories identified in the following table: 

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Target Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> The collector load module. </td> 
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> The transmitter program. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> The Sensor configuration file. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> The certificate used to validate the digital certificate that Insight Server presents during the connection process </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The installation package contains a spreadsheet file called TestExperiment.xls. This spreadsheet is a tool that architects use to configure a controlled experiment. Sensor itself does not use this file, so it is not necessary to install the file on the machine where Sensor is running (although you can choose to do so). You might want to, instead, copy the file to a location where your architects can access it or simply extract the file from the installation package as needed. For more information about controlled experimentation, see the Insight Controlled Experiments Guide.

**Permissions on the Program Files**

>[!NOTE]
>
>Incorrect permissions on the program files cause the majority of problems encountered when installing Sensor. Please make sure that you set the permissions exactly as stated in this section. 
>
>By default, the program files in the tar file have the following permissions. Depending on how your system is configured, these settings might be altered (unmasked) when you extract the files. To reset the permissions to the recommended default settings, use the chmod commands below. Check that the directories into which you have installed the files permit at least this level of access.

|  File  | Default Permissions  | chmod command  |
|---|---|---|
|  mod_visual_sciences.so  | rwx r-x r-x  | chmod 775  |
|  txlogd  | rwx --x --x  | chmod 711  |
|  txlogd.conf  | rw- r-- r--  | chmod 664  |
|  trust_ca_cert.pem  | rw- r-- r--  | chmod 664  |

## Enable Logging on the Sametime Server {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Steps that allow you to log on to the Sametime Server.

1. Use the Lotus Domino Administrator client to connect to the Lotus Domino server that is running Sametime. 
1. In the Lotus Domino Administrator, click the Files tab, then double-click Sametime Configuration - stconfig.nsf to open the Sametime Configuration file. 
1. In the Sametime Configuration file, open the Community Services form and double-click anywhere on the form to enter edit mode. 
1. Set Chat Logging Flag to “strict” and Capture Service Type to “0x1000.” 
1. Save and close the Community Services form, then close the Sametime Configuration file. 
1. Restart the Sametime server.

## Edit the Sensor Configuration File {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

For IBM HTTP servers, the collector is a dynamic shared object that you load into your web server process.

To add the collector to your web server, you must edit the httpd.conf file as described below and restart your web server.

If Sensor is capturing data for multiple web servers on the server computer, you must perform the following procedure for each web server.

1. Using a text editor, open the httpd.conf file for the web server whose events Sensor captures. 
1. Add the following two lines to the end of the file: 

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >These lines are case sensitive. Type them exactly as they appear above.

1. Restart the web server process (you do not have to reboot the entire server computer, simply restart the web server process). The collector is loaded with the web server and begins collecting event data and writing it to the disk queue.

## Test the Sensor {#section-0dae181ef8884f10a57f6cfda8500969}

Verify that the collector is collecting event data and the transmitter is transmitting it to the target Insight Server.

>[!NOTE]
>
>To verify that the transmitter can successfully send event data to the Insight Server, make sure that the target Insight Server is installed and running before you begin the following test.

1. If the transmitter is not already running, restart it using the following command:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Open a browser (on any machine) and request a page from the web server on which Sensor is running (be sure to select a page that Sensor is monitoring). 
1. After you issue the request, check the transmitter’s console for messages indicating that it is sending event data to the target Insight Server. 
1. f Sensor is not transmitting data successfully, verify that:

    * The target Insight Server is running. 
    * The ServerAddress and ServerPort parameters are set correctly in txtlogd.conf. If you specified ServerAddress using a server name, try using its numeric IP address instead. 
    * The value of the CertName parameter matches the common name that appears on the digital certificate of the target Insight Server exactly.

## Add the Transmitter to System Startup Script {#section-19a38f27c9f44adf88f8910f5ed483a3}

Information about automatically loading the transmitter to your system startup script.

To ensure that the transmitter loads automatically when the web server machine is restarted, add the following command (which launches the transmitter) to your system startup script:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

This command starts the transmitter as a daemon. Operating and error messages that the transmitter generates are written to syslog. 
