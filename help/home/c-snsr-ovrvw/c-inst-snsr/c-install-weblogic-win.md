---
description: Detailed instructions for installing and configuring Sensor for WebLogic Server 6.x or later running under Microsoft Windows Server 2000 or later.
title: WebLogic Server on Windows Server 2000 or Later
uuid: 80dbf544-bd09-4af8-bb05-4032eb49dd5d
exl-id: cf5b5284-dd61-4c55-8319-483bfe60930c
---
# WebLogic Server on Windows Server 2000 or Later{#weblogic-server-on-windows-server-or-later}

Detailed instructions for installing and configuring Sensor for WebLogic Server 6.x or later running under Microsoft Windows Server 2000 or later.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

To install and configure Sensor, you must perform the following steps:

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedure to extract and install the program files for Sensor.

1. On your WebLogic Server, create a directory in which to install the Sensor program files. Keep in mind that your disk queue resides in this directory, so be sure the device you choose has sufficient space to hold a queue of the size you need. 

   ```
   C:\VisualSensor
   ```

1. Extract the contents of the installation file into the directory you just created. During this step, Sensor installs the following files: 

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
   <td colname="col1"> visual_sciences.dll </td> 
   <td colname="col2"> The collector load module. </td> 
   <td colname="col3"> In any directory. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> The collector load module libraries </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> The transmitter program. </td> 
   <td colname="col3"> In any directory </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> The Sensor configuration file. </td> 
   <td colname="col3"> In any directory </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> The certificate used to validate the digital certificate that Insight Server presents during the connection process </td> 
   <td colname="col3"> In any directory </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The installation package contains a spreadsheet file called [!DNL TestExperiment.xls]. This spreadsheet is a tool that architects use to configure a controlled experiment. Sensor itself does not use this file, so it is not necessary to install the file on the machine where Sensor is running (although you can choose to do so). You might want to, instead, copy the file to a location where your architects can access it or simply extract the file from the installation package as needed. For more information about controlled experimentation, see the Insight Controlled Experiments Guide.

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

1. From the Start menu in Windows, select Accessories > Command Prompt. 
1. In the command prompt window, navigate to the directory in which you installed Sensor and execute the following command:

   ```
   txlog /regserver
   ```

   This command starts the transmitter, creates the disk queue, and registers Sensor as a Windows service. 

1. To confirm that the transmitter is running correctly, click Start > Control Panel > Administrative Tools > Services. 

   >[!NOTE]
   >
   >This command sequence might vary depending on which version of Windows you are using.

    1. In the service list, locate the entry for Sensor and confirm that its status is Started and its startup type is Automatic. 
    1. Close the Services control panel.

1. To check whether transmitter experienced any errors during start-up, click Start > Control Panel > Administrative Tools > Event Viewer to open the Event Viewer.

    1. In the left pane of the Event Viewer window, select the Applications log. 
    1. In the right pane, look for events with “Adobe” in the Source column. 
    1. If you find an error from “Adobe,” double-click the error to display the Event Properties window. This window provides detailed information about the error.

1. When you finish examining the Applications log, close the Event Viewer. 
1. Verify that the transmitter has created the disk queue (Diskq2000.log) in the directory where you installed the Sensor program files and that it is the size that you specified in the QueueSize parameter in the txlogd.conf file.

   If the queue has not been created correctly:

    1. Examine the txtlogd.conf file and verify that the QueueSize parameter is set correctly. 
    1. Check that the device on which you installed Sensor has sufficient space available to hold a file of the size specified in the QueueSize parameter. 
    1. Using the Services control panel in Windows, stop the transmitter. 
    1. Delete the queue file. 
    1. Re-register Sensor as a Windows service: from the Start menu in Windows, select Accessories > Command Prompt. In the command prompt window, navigate to the directory in which you installed Sensor and execute the following command:     
    
       ```    
       txlog /regserver
       ```

The transmitter is designed to run continuously. If you restart the machine, the transmitter restarts automatically. If you need to start and stop the transmitter manually, you can do so using the Services control panel in Windows.

## Add the Collector to the Web Server {#section-c5b83ae4ebce430aa764f951e849b333}

For JBoss servers, the collector operates as a filter in the servlet container.

To add the collector to your web server, you must edit the [!DNL web.xml] file as described below and restart your web application.

1. Using a text editor, open the [!DNL web.xml] file for the web server whose events Sensor captures. 
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

1. Restart the web server process (you do not have to reboot the entire server computer, simply restart the web server process). The collector is loaded with the web server and begins collecting event data and writing it to the disk queue.

## Modify the Startup Script {#section-0dae181ef8884f10a57f6cfda8500969}

Instructions for startup script modification.

In the script that is used to start WebLogic (for example, C:\bea\user_projects\mydomain\startServer.cmd), edit the “set JAVA_OPTIONS=” line to set the java.library.path definition to the directory containing the visual_sciences.dll file.

```
set JAVA_OPTIONS=-Djava.library.path=C:\Sensor 
    directory
```

## Capturing Additional Data {#section-9483b663cbd0432daaca50c1089c7fca}

You can capture additional measurement data from J2EE-based web applications using the appendToLog() functionality.

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
