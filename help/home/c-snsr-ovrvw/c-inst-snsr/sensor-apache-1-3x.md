---
description: Detailed instructions for installing and configuring Sensor for an Apache Server 1.3.x on RedHat Linux 7.x or later, SUSE Linux 9.x or later, Sun Solaris SPARC 2.6 or later, Sun Solaris x86 9 or later, FreeBSD 4 or later, or Mac OS X PowerPC.
title: Apache Server 1.3.x on Linux, Sun Solaris, FreeBSD, or Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
---
# Apache Server 1.3.x on Linux, Sun Solaris, FreeBSD, or Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Detailed instructions for installing and configuring Sensor for an Apache Server 1.3.x on RedHat Linux 7.x or later, SUSE Linux 9.x or later, Sun Solaris SPARC 2.6 or later, Sun Solaris x86 9 or later, FreeBSD 4 or later, or Mac OS X PowerPC.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

To install and configure Sensor, you must perform the following high-level steps:

## Install the Program Files {#section-aae323e252394212bf4096d65fdd280c}

Instructions to extract and install the program files for Sensor to the server machine.

1. Log on as the root user or as a user with root authority. 
1. Decompress and unpack the installation file using the following command:

    * On Linux:     
    
      ```    
      tar -zxf installationFilename.tar.gz
      ```    
    
    * On Solaris:     
    
      ```    
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copy the unpacked program files to the directories identified in the following table: 

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> The collector load module </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> The transmitter program </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> The Sensor configuration file </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> The certificate used to validate the digital certificate that Insight Server presents during the connection process </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >The installation package contains a spreadsheet file called TestExperiment.xls. This spreadsheet is a tool that architects use to configure a controlled experiment. Sensor itself does not use this file, so it is not necessary to install the file on the machine where Sensor is running (although you may choose to do so). You might want to, instead, copy the file to a location where your architects can access it or simply extract the file from the installation package as needed. For more information about controlled experimentation, see the Insight Controlled Experiments Guide.

**Permissions on the Program Files**

Incorrect permissions on the program files cause the majority of problems encountered when installing Sensor.

Please make sure that you set the permissions exactly as stated in this section.

By default, the program files in the tar file have the following permissions. Depending on how your system is configured, these settings might be altered (unmasked) when you extract the files. To reset the permissions to the recommended default settings, use the chmod commands below. Check that the directories into which you have installed the files permit at least this level of access. 

|  File  | Default Permissions  | chmod command  |
|---|---|---|
|  mod_visual_sciences.so  | rwx r-x r-x  | chmod 755  |
|  txlogd  | rwx --x --x  | chmod 711  |
|  txlogd.conf  | rw- rw- r--  | chmod 664  |
|  trust_ca_cert.pem  | rw- rw- r--  | chmod 664  |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

The [!DNL txlogd.conf] file contains the configuration parameters for Sensor.

You must edit the file to specify, among other things, the size of the disk queue, the address of the Insight Server, and the ID that will be attached to the data produced by this sensor.

The configuration file contains required parameters and optional parameters.

* Required parameters are settings that you must specify when you install Sensor. Without these settings, Sensor does not run successfully. 
* Optional parameters are settings that default to pre-defined values (which you can modify) or enable optional features.

To edit the Sensor configuration file

1. Open the /etc/txlogd.conf file in a text editor and set the required parameters as well as any desired optional parameters. 
1. Save and close the file.

## Start the Transmitter and Create the Disk Queue {#section-a453d912ec3d47aa8e40ccacf527119d}

Instructions to create the disk queue after you configure the txlogd.conf file.

1. If the directory in which the disk queue resides does not already exist, create it. Make sure that the directory provides both the collector module and the transmitter program with read/write access to the file. 
1. On the computer where Sensor is installed, execute the following command to start the transmitter: 

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

    * The “i” option in this command starts the transmitter in interactive mode. This mode displays transmitter messages on the screen and also enables you to interact with the transmitter using keyboard commands. 
    * The “c” option directs the transmitter to create the disk queue. 
    * The “f” option specifies the location of the configuration file.

1. Verify that the transmitter has created the disk queue in the location specified in the QueueFile parameter and of the size specified in the QueueSize parameter. 
1. If the queue has not been created correctly, type Ctrl+C to terminate the transmitter, then do the following:

    1. Examine the txtlogd.conf file and verify that the QueueFile and QueueSize parameters are set correctly. 
    1. Check that the device to which the disk queue is assigned is operational and has sufficient space available to hold a file of the size specified in the QueueSize parameter. 
    1. Make any necessary corrections and repeat this procedure.

## Add the Collector to the Web Server {#section-a7fb6425956f4f518ae3a7db091b33d2}

For Apache servers, the collector is a dynamic shared object that you load into your web server process.

To add the collector to your web server, you must edit the httpd.conf file as described below and restart your web server.

If Sensor is capturing data for multiple web servers on the server computer, you must perform the following procedure for each web server.

1. Using a text editor, open the [!DNL httpd.conf] file for the web server whose events Sensor captures. 
1. Add the following lines to the end of the file: 

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >These lines are case sensitive. Type them exactly as they appear above.

1. Restart the web server. The collector is loaded with the web server and will begin collecting event data and writing it to the disk queue.

## Test the Sensor {#section-83d9f60b39a6474f9c76bee3e19b2575}

Start the transmitter and verify that it can successfully connect to the Insight Server and transmit event data to it.

>[!NOTE]
>
>To verify that the transmitter can successfully send event data to the Insight Server, make sure that the target Insight Server is installed and running before you begin the following test.

1. If the transmitter is not already running, restart it using the following command:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Open a browser (on any machine) and request a page from the web server on which Sensor is running (be sure to select a page that Sensor is monitoring). 
1. After you issue the request, check the transmitter’s console for messages indicating that it is sending event data to the target Insight Server. 
1. If Sensor is not transmitting data successfully, verify that:

    * The target Insight Server is running. 
    * The [!DNL ServerAddress] and [!DNL ServerPort] parameters are set correctly in [!DNL txtlogd.conf]. 
    
    * If you specified [!DNL ServerAddress] using a server name, try using its numeric IP address instead. The value of the [!DNL CertName] parameter matches the common name that appears on the digital certificate of the target Insight Server exactly.

## Add the Transmitter to Your System Startup Script {#section-4e1ffa6e043941ab91411d91d596477a}

Information to ensure that the transmitter loads automatically when the web server machine is restarted.

Add the following command (which launches the transmitter) to your system startup script. 

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

This command starts the transmitter as a daemon. Operating and error messages that the transmitter generates are written to syslog.

>[!NOTE]
>
>Some Solaris users might encounter an “unable to acquire mutex” error. For Sensor to function properly on these systems, the following line needs to either be added to or edited in the file /etc/system:
>
>```
>semsys:seminfo_semmnu=1024
>```
>
>The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.”
