---
description: Instructions for installing and configuring Sensor on the family of web servers that evolved from the original Netscape Enterprise Web Server running on Linux or Solaris machines. Includes Netscape Enterprise, iPlanet, Sun ONE, and Sun Java System Servers on Linux or Solaris.
seo-description: Instructions for installing and configuring Sensor on the family of web servers that evolved from the original Netscape Enterprise Web Server running on Linux or Solaris machines. Includes Netscape Enterprise, iPlanet, Sun ONE, and Sun Java System Servers on Linux or Solaris.
seo-title: Netscape Enteprise on Linux or Solaris
title: Netscape Enteprise on Linux or Solaris
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
---

# Netscape Enteprise on Linux or Solaris{#netscape-enteprise-on-linux-or-solaris}

Instructions for installing and configuring Sensor on the family of web servers that evolved from the original Netscape Enterprise Web Server running on Linux or Solaris machines. Includes Netscape Enterprise, iPlanet, Sun ONE, and Sun Java System Servers on Linux or Solaris.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

Sensor supports the following servers running under RedHat Linux 7.x or later or Sun Solaris SPARC 2.6 or later:

* Netscape Enterprise Server 3.6 or later 
* iPlanet Web Server 4.0 or later

Sensor supports these servers running under RedHat Linux 7.x or later or Sun Solaris 8.x or later:

* Sun ONE Web Server 6.0 or later 
* Sun Java System Web Server 6.1 or later

Sensor supports these servers running under Sun Solaris x86 9 or later:

* Sun Java System Web Server 6.1 or later

>[!NOTE]
>
>The installation file for this family of web servers is listed as the “Netscape Solaris Sensor” or “Netscape LINUX Sensor” on the Adobe download site.

To install and configure Sensor, you must perform the following steps:

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedure to extract and install the program files for Sensor.

1. Log on as the root user or as a user with root authority. 
1. Decompress and unpack the installation file using the following command:

   ```
   gunzip installationFilename.tar.gz 
        
       tar -xf installationFilename.tar
   ```

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
   <td colname="col1"> aol_visual_sciences.so </td> 
   <td colname="col2"> The collector load module. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
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

****

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

## Add the Collector to the AOL Server {#section-c5b83ae4ebce430aa764f951e849b333}

For AOLServer, the collector is a dynamic shared object that you load into your web server process.

To add the collector to your AOL server, you must edit the configuration file for your server as described below and restart your AOL server. Usually the server’s configuration file is named nsd.tcl and is located in the directory where AOL Server is installed.

1. Open the configuration file in a text editor and locate the following section:

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. Add the following line. (Add as a single statement. Ignore word wrap shown below.)

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   
   ```

1. Create a new section as follows.

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. To this new section, add the line:

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >These lines are case sensitive. Type them exactly as they appear above.

1. Restart the AOL server. The collector is loaded and will begin collecting event data and writing it to the disk queue.

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

This command starts the transmitter as a daemon. Operating and error messages that the transmitter generates are written to [!DNL syslog].

The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.” 
