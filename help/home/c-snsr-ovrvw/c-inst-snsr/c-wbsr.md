---
description: Detailed instructions for installing and configuring Sensor for WebSphere 5.x running on AIX 5.1 or later.
solution: Insight
title: WebSphere on AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
---

# WebSphere on AIX{#websphere-on-aix}

Detailed instructions for installing and configuring Sensor for WebSphere 5.x running on AIX 5.1 or later.

The program files for [!DNL Sensor] are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the [!DNL Sensor] installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

>[!NOTE]
>
>The [!DNL Sensor] for WebSphere servers does not support controlled experimentation. For information about controlled experimentation, see the *Data Workbench Controlled Experiments Guide.*

## Install the Program Files {#section-86f69127278c41bc90b97b68bb40bc6e}

Procedure to extract and install the program files for Sensorto the server machine.

1. Log on as the root user or as a user with root authority. 
1. Decompress and unpack the installation file using the following command: 

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Copy the unpacked program files to the directories identified in the following table: 

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Target Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> The collector load module </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> The collector load module libraries </td> 
   <td colname="col3"> WebSphere /lib directory </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
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

By default, the program files in the tar file have the following permissions. Depending on how your system is configured, these settings might be altered (unmasked) when you extract the files.

To reset the permissions to the recommended default settings, use the chmod commands below. 

>[!NOTE]
>
>Check that the directories into which you have installed the files permit at least this level of access.

|  File  | Default Permissions  | chmod command  |
|---|---|---|
|  libvisual_sciences.so  | rwx --x --x  | chmod 711  |
|  J2EECollector.jar  | rw- rw- r--  | chmod 664  |
|  txlogd  | rwx --x --x  | chmod 711  |
|  txlogd.conf  | rw- rw- r--  | chmod 664  |
|  trust_ca_cert.pem  | rw- rw- r--  | chmod 664  |

If you want to use permissions other than the recommended defaults, review the information in Sensor UNIX File Permissions, to be sure you understand how these files are used.

## Edit the Sensor Configuration file {#section-283c8a92fa8841c1b6034e5f834ef4e7}

The txlogd.conf file contains the configuration parameters for Sensor.

You must edit the file to specify, among other things, the size of the disk queue, the address of the Insight Server, and the ID that will be attached to the data produced by this sensor.

The configuration file contains required parameters and optional parameters.

* Required parameters are settings that you must specify when you install Sensor. Without these settings, Sensor does not run successfully. 
* Optional parameters are settings that default to pre-defined values (which you can modify) or enable optional features.

**To edit the configuration file**

1. Open the /etc/txlogd.conf file in a text editor and set the required parameters as well as any desired optional parameters. 
1. Save and close the file.

## Start the Transmitter and Create the Disk Queue {#section-63285a2328604f20a2cb31b3d5cb80e6}

Procedure to create the disk queue, after you configure the txlogd.conf file.

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

## Add the Collector to the Web Application {#section-d17297b1193f4e3cb150fb41f754ef12}

For WebSphere servers, the collector operates as a filter in the servlet container.

To add the collector to the web application, add the filter to the web application’s web.xml deployment descriptor and restart the web application.

1. Using a text editor, open the web.xml file for the web server whose events Sensor captures. 
1. Add the following `<filter>` and `<filter-mapping>` elements to the descriptor file. If you did not install txlogd.conf in the /etc directory, you need to enter the correct path to this file in the `<param-value>` element.

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
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

1. Restart the web application. The collector is loaded with the application and will begin collecting event data and writing it to the disk queue.

## Declare the Location of the Collector and Shared Object Files {#section-e641f08999d34a648aaee2111b69ca25}

Procedure to edit the Websphere startup script to declare the location of the J2EECollector.jar and libvisual_sciences.so files.

1. Open the setupCmdLine.sh file in the Websphere /bin directory. 
1. After the line that defines the $WAS_CLASSPATH variable, add the following line: 

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. After the case block that defines the $WAS_LIBPATH variable, add the following line:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Save the [!DNL setupCmdLine.sh] file.

## Test the Sensor {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

Procedure to start the transmitter and verify that it can successfully connect to the Insight Server and transmit event data to it. 

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
    * The ServerAddress and ServerPort parameters are set correctly in txtlogd.conf. If you specified ServerAddress using a server name, try using its numeric IP address instead. 
    * The value of the CertName parameter matches the common name that appears on the digital certificate of the target Insight Server exactly.

## Add the Transmitter to Your System Startup Script {#section-23bb905100d04f018af93873dd4d5f68}

Information to ensure that the transmitter loads automatically when the web server machine is restarted.

Add the following command (which launches the transmitter) to your system startup script. 

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

This command starts the transmitter as a daemon. Operating and error messages that the transmitter generates are written to syslog.

## Capturing Additional Data {#section-d5ccf8ee50914a87938e0c17480757e6}

Sensors for all platforms can collect any of the data available in the HTTP request and response headers.

The Sensors for the J2EE Platform provide a mechanism for collecting data that is not available on other platforms. The collector for the J2EE platform (J2EE collector) sits on the application layer, which enables it to collect sensitive data that is available only to the application and should not be exposed through page tagging or in the headers.

>[!NOTE]
>
>While page tags and header modification can hide the data, it is still available to those who examine the source code of a page or look at the headers using browser plug-in tools.

For example, the J2EE collector can be used to capture cost per click (CPC) data for links displayed on a page, sensitive partner information on a page, and many other data points. The J2EE environment makes it easy for you to modify your WEBAPP to capture this custom data using our collector class.

When a Sensor for the J2EE Platform receives a request, it invokes a collector class that imports the appendToLog function. The appendToLog function appends to the initial request the query string parameters specified in the appendToLog function. This results in the URI of the initial request containing additional query string name-value pairs that correspond to the names and values of the data that is being captured. For example, CPC=20 would be appended to the initial request when the value of a particular ad placement or click-through link is 20 cents. Insight Server processes these values into the dataset for analysis. One additional benefit to this collection methodology is that it allows the collection of additional data without creating extra log entries, as might be created using page tagging methodologies.

For more information about processing, see the *Dataset Configuration Guide*.

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

