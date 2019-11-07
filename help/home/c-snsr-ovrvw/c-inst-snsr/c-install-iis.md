---
description: Instructions about how to install and configure Sensor for Internet Information Services (IIS) 5.x or 6.x running under Microsoft Windows Server 2000 or later.
title: Microsoft IIS on Windows Server 2000 or later
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
---

# Microsoft IIS on Windows Server 2000 or later{#microsoft-iis-on-windows-server-or-later}

Instructions about how to install and configure Sensor for Internet Information Services (IIS) 5.x or 6.x running under Microsoft Windows Server 2000 or later.

When using IIS 6.x, logging must be enabled for Sensor to function properly. If you have disabled logging to reduce disk I/O, you can enable logging without writing any data to the logs. To do so, enable logging, then clear all of the fields on the Advanced tab of the Properties for the W3C Extended Log File Format. If you need assistance, contact Adobe Consulting Services.

The program files for Sensor are packaged in an installation file that you obtain from the Adobe download site. If you do not already have the Sensor installation file for your particular web server, download it (or obtain it from your Adobe representative) before you begin the following procedures.

To install and configure Sensor, you must perform the following high-level steps:

## 1. Install the Program Files {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

When running Sensor on Windows IIS, the program files and the disk queue file must reside in the same directory.

Therefore, before installing the program files, you must determine where you want to maintain the disk queue, because that is also where you must install the program files.

Use the following procedure to extract and install the program files for Sensor.

1. On your Windows machine, create a directory in which to install the Sensor program files. Keep in mind that your disk queue also resides in this directory, so be sure the device you choose has sufficient space to hold a queue of the size you need.

   For example: C:\VisualSensor 

1. Extract the contents of the installation file into the directory you just created. During this step, Sensor installs the following files:

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
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
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> The collector module (an ISAPI filter). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestExperiment.xls </td> 
   <td colname="col2"> <p>An Excel spreadsheet file that architects can use to configure a controlled experiment. </p> <p>Sensor does not use this file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> The certificate used to validate the digital certificate that Insight Server presents during the connection process. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> The transmitter program. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> The Sensor configuration file. </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >The installation package contains a spreadsheet file called TestExperiment.xls. This spreadsheet is a tool that architects use to configure a controlled experiment. Sensor itself does not use this file, so it is not necessary to install the file on the machine where Sensor is running (although you can choose to do so). You might want to, instead, copy the file to a location where your architects can access it or simply extract the file from the installation package as needed. For more information about controlled experimentation, see the Insight Controlled Experiments Guide.

## 2. Edit the Configuration File {#section-206daf855e664f16af9a96a5cd3e62b1}

The txlogd.conf file contains the configuration parameters for Sensor.

You must edit the file to specify, among other things, the size of the disk queue, the address of the Insight Server, and the ID that will be attached to the data produced by this sensor. The configuration file contains required parameters and optional parameters.

* **Required parameters** are settings that you must specify when you install Sensor. Without these settings, Sensor does not run successfully. 
* **Optional parameters** are settings that default to pre-defined values (which you can modify) or enable optional features.

**To edit the Sensor configuration file**

1. Open the `<SensorDirectory>/txlogd.conf` file in a text editor and set the required parameters as well as any desired optional parameters.

   For descriptions of txlogd.conf parameters, see Sensor Txlogd.conf File Parameters.

   For examples of completed configuration files, see Sensor Sample Configuration Files. 

1. Save and close the file.

## 3. Start the Transmitter and Create the Disk Queue {#section-a0af390ee1954109bcff5d9f09798683}

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

   >[!NOTE]
   >
   >This command sequence might vary depending on which version of Windows you are using.

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

## Add the Collector to the Web Server {#section-682dc480e5574791ac18da104daf7906}

For IIS, the collector is an ISAPI filter that you add to your web server in IIS.

1. Open the IIS Manager using Start > Administrative Tools > Internet Information Services (IIS) Manager. 
1. Expand the Local Computer and Web Sites nodes. 
1. Right-click the website to which you want to add the collector and select Properties. 
1. Select the ISAPI Filters tab and click Add. 
1. In the Filter Name field, enter a display name for the filter. The suggested filter name is “Sensor.” 
1. Click Browse, select the qlog.dll file (located in the directory where you installed Sensor), and click OK. 
1. Click OK to add the filter.

   After you add the filter, the collector is immediately operational and ready to collect data. An upward green arrow should appear in the Status column on the ISAPI Filters tab of the IIS Manager. You might not see the green arrow until traffic actually flows through the filter. In this case, you need to submit a request to the web server to confirm that the collector is operating correctly.

If the green arrow does not appear after traffic flows to the collector, complete the following steps:

1. Click Start > Administrative Tools > Event Viewer to check the Event Viewer for errors. 

   >[!NOTE]
   >
   >This command sequence might vary depending on which version of Windows you are using.

1. In the left pane of the Event Viewer window, select the Application log. 
1. In the right pane, look for events with “Adobe” in the Source column. 
1. If you find an error, double-click the error to display the Event Properties window.

## Capturing Additional Data {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

Web pages are often structured using ASP (Active Server Pages) programming language.

ASP is a Microsoft technology that runs within IIS. When a browser requests an ASP file, IIS passes the request to the ASP engine. The ASP engine reads the ASP file, line by line, and executes the scripts in the file. Finally, the ASP file is returned to the browser as plain HTML. ASP provides RESPOND or REQUEST objects which, in addition to other utilizations, allow the response or request of user queries or data submitted from HTML forms.

In certain cases, you may not want to append the values entered into forms to the URL that is displayed within the Address bar of a user’s browser or that is viewable within the HTML code itself. Simple server-side ASP Script lets you append form field names and their respective values to the log file without making them available within the user’s browser or embedding them into the HTML file. To capture the actual form values entered into particular forms within your website, a few lines of code must be added to append the form values to the log request.

Within the processing page of a form, include the following code to append the entered form values to the request data (in addition to writing the submitted form values to an external database or other location):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

This process would append the form values as defined to the request data for the Form Processing page. Within the log data, the appended values would be available as query strings of the Form Processing page as illustrated below. For example, v_1, v_2, v_3 and v_4 would now be query strings containing the data entered into the appropriate form fields. The syntax described in the previous example can be duplicated for any additional form fields and values that you want to capture:

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

If you want every form field and value to be captured and available for analysis, you can use the following syntax: 

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

This example would take all form fields present within the HTML along with their respective values and append them as query strings to the log entry for the Form Processing page. Please note that this would include any hidden fields present within the form.

The log data would be augmented as detailed in the following table:

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_1  | Value associated with the NAME query string  | v_1=John Smith  |
|  v_2  | Value associated with the CITY query string  | v_2=Los Angeles  |
|  v_3  | Value associated with the STATE query string  | v_3=California  |
|  v_4  | Value associated with the ZIP query string  | v_4=90210  |

