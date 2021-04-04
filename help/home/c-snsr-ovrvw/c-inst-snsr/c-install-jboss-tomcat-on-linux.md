---
description: Detailed instructions for installing and configuring Sensor for J2EE implementations running on RedHat Linux 7.x or later, Sun Solaris SPARC 2.6 or later, or Sun Solaris x86 9 or later.
title: JBoss, Tomcat, and WebLogic Servers on RedHat Linux or Sun Solaris
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
exl-id: 09c2f266-2ecc-42fc-98b6-b91f8883af0c
---
# JBoss, Tomcat, and WebLogic Servers on RedHat Linux or Sun Solaris{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

Detailed instructions for installing and configuring Sensor for J2EE implementations running on RedHat Linux 7.x or later, Sun Solaris SPARC 2.6 or later, or Sun Solaris x86 9 or later.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

Supported J2EE implementations include:

* JBoss Server 3.2.x or later 
* Apache Jakarta Tomcat Server 4.1 or later 
* WebLogic Server 6.x or later

To install and configure Sensor, you must perform the following steps:

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedure to extract and install the program files for Sensor.

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
1. Add the following `<filter>` and `<filter-mapping>` elements to the descriptor file. If you did not install txlogd.conf in the /etc directory, you need to enter the correct path to this file in the `<param-value>` element: 

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
    
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
   
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

This command starts the transmitter as a daemon. Operating and error messages that the transmitter generates are written to [!DNL syslog].

The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.”

## Capturing Additional Data {#section-9483b663cbd0432daaca50c1089c7fca}

Sensors for all platforms can collect any of the data available in the HTTP request and response headers.

The Sensors for the J2EE Platform provide a mechanism for collecting data that is not available on other platforms. The collector for the J2EE platform (J2EE collector) sits on the application layer, which enables it to collect sensitive data that is available only to the application and should not be exposed through page tagging or in the headers. 

>[!NOTE]
>
>While page tags and header modification can hide the data, it is still available to those who examine the source code of a page or look at the headers using browser plug-in tools.

For example, the J2EE collector can be used to capture cost per click (CPC) data for links displayed on a page, sensitive partner information on a page, and many other data points. The J2EE environment makes it easy for you to modify your WEBAPP to capture this custom data using our collector class.

When a Sensor for the J2EE Platform receives a request, it invokes a collector class that imports the appendToLog function. The appendToLog function appends to the initial request the query string parameters specified in the appendToLog function. This results in the URI of the initial request containing additional query string name-value pairs that correspond to the names and values of the data that is being captured. For example, CPC=20 would be appended to the initial request when the value of a particular ad placement or click-through link is 20 cents. Insight Server processes these values into the dataset for analysis. One additional benefit to this collection methodology is that it allows the collection of additional data without creating extra log entries, as might be created using page tagging methodologies.

For more information about processing, see the Dataset Configuration Guide.

**To capture additional data from a page**

1. Add the following code to the top of the .jsp page from which you want to capture data:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Use the appendToLog() method of the collector object to append the desired name-value pairs to the requested .jsp page's query string. The following example appends “A=1” and “B=2” to the requested .jsp page’s query string for the /index.jsp page:

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   The resulting request URI is /index.jsp?A=1&B=2. 

1. Repeat this procedure for each .jsp page from which you want to capture additional data.
