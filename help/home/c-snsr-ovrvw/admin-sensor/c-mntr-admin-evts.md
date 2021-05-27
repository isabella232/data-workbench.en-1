---
description: To detect Sensor errors as soon as possible and repair them before they cause major problems or outages, you should regularly monitor your Event logs.
title: Monitoring Administrative Events
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
---
# Monitoring Administrative Events{#monitoring-administrative-events}

To detect Sensor errors as soon as possible and repair them before they cause major problems or outages, you should regularly monitor your Event logs.

 **Recommended Frequency:** At least hourly

You can monitor these events using the Windows Event Viewer or Unix Syslog file and the [!DNL *.sensor-log] files located by default in the [!DNL Logs] folder within the [!DNL Sensor] installation directory. These files indicate the presence of errors during data collection, especially if a [!DNL Sensor] cannot connect to the target [!DNL data workbench server] and starts queuing data.

## Monitoring Events on Windows {#section-7c0443a356af4381bf22259654f5cd17}

Sensor logs errors to the Application Log of the Windows Event Viewer with a source of “Adobe.”

Messages are logged as “Information,” “Warning,” or “Error” depending on their severity.

**To open the Windows Event Viewer**:

* Click **Start > Control Panel > Administrative Tools > Event Viewer**.

## Monitoring Events on Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Sensor logs errors to the [!DNL syslog] daemon.

The syslog daemon writes error messages to log files based on the rules you specified in your syslog.conf file. Errors are logged with the flags “LOG_DAEMON” and either “LOG_NOTICE” or “LOG_ERR,” depending on severity.

**To open the Unix syslog**

The Unix syslog is typically located in [!DNL /var/adm/messages] or [!DNL /var/log/messages].

Browse to the appropriate location and open the syslog.

## Understanding Message Formats {#section-a0899add30fd4b2da58a23b9e3324693}

All Sensor messages contain the string “Sensor” and are numbered to reflect the importance of the message being displayed.

|  Message Number  | Message Meaning  | Message String  |
|---|---|---|
|  1xxx  | Informational  | Sensor Info #  |
|  2xxx  | Warning  | Sensor Warning #  |
|  3xxx  | Configuration Error  | Sensor Error #  |
|  4xxx  | Operational Error  | Sensor Error #  |
|  5xxx  | Internal Error  | Sensor Error #  |

>[!NOTE]
>
>Warnings (2xxx) are not currently in use. These numbers are reserved for future use.

Your network management tool can be set to monitor your messages every 5-10 minutes for errors with the “Sensor” source and alert appropriate personnel about issues that may require intervention. You can choose to monitor the system for only certain types of Event messages, such as the “Sensor Error” string. Alternatively, you can apply different rules to events prefaced with “Sensor Info,” “Sensor Warning,” and “Sensor Error” strings.

## Identifying Important Messages {#section-5a20f5dc18ca4012931d194db855e54e}

Within your event logs, you should pay special attention to and immediately address any messages regarding queue size.

For example, messages such as “ [!DNL Sensor Info 1012: Adobe disk queue is #% full]” need attention.

## Responding to Sensor Event Messages {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tables that describe Sensor events and suggested actions for the supported web server platforms.

**All Platforms** 

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event Message </th> 
   <th colname="col2" class="entry"> Suggested Action </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sensor Info 1010: Sensor initialized. </td> 
   <td colname="col2"> No action required. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1011: Sensor terminated. Total clicks queued ## </td> 
   <td colname="col2"> No action required. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1012: Adobe disk queue is #% full </td> 
   <td colname="col2"> This message is logged each time the disk queue utilization crosses a 10% threshold. If this percentage continues to grow, action should be taken before the queue is full and data is lost. The most likely problem is that the Sensor has stopped communicating with the Insight Server. Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1013: Sensor configuration changed </td> 
   <td colname="col2"> No action required. The Sensor detected a change in one of its configuration files and will reload. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1014: Problem seeding random number generator </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1016: Config file file name loaded </td> 
   <td colname="col2"> No action required. The Sensor successfully loaded the configuration file listed. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1017: Experiment file file name loaded </td> 
   <td colname="col2"> No action required. The Sensor successfully loaded the experiment file listed. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 3016: Unable to load config file /mypath/myfile </td> 
   <td colname="col2"> Confirm that the Sensor configuration file specified in the web server configuration exists and has the required permissions to be read by the web server process. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: Unable to load controlled experiment configuration file /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Confirm that the controlled experiment file specified in txlogd.conf exists and that the txlogd process has the necessary permissions to read the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 3018: Unable to parse content filter lists. Check txlogd configuration file </td> 
   <td colname="col2"> Verify the syntax of the ContentFilterInclude and ContentFilterExclude entries in txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 3023: Failed to create lock (g_lockThrottle) </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 3024: Failed to create lock (g_lockConfigCheck) </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 4014: Could not open disk queue. </td> 
   <td colname="col2"> Verify QueueFile file name in txlogd.conf and if believed to be correct, contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 4020: Not a queue file </td> 
   <td colname="col2"> Verify QueueFile file name in txlogd.conf and if believed to be correct, contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 4021: Queue is full </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 4022: Unable to map memory block of length &lt;x&gt; at offset &lt;y&gt; </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5012: Could not create mutex. </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5013: Could not acquire mutex. </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5030: Spawn fork error. </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5031: setsid failed. </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5032: Spawn fork error. </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5033: chdir failed. </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5034: Signal received </td> 
   <td colname="col2"> Program was likely terminated by an external signal. If the source of this signal cannot be determined, contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5035: Exit called from outside main </td> 
   <td colname="col2"> Contact Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Error 5036: txlogd is already running </td> 
   <td colname="col2"> Another instance of the txlogd daemon is already running. Stop the other instance first if you want to run a new one. </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server** 

|  Event Message  | Suggested Action  |
|---|---|
|  Sensor Error 3015: The VisualSciencesConfig directive is missing from httpd.conf.  | This is a configuration error. The VisualSciencesConfig directive must be in httpd.conf with a parameter that is the location of txlogd.conf.  |
|  Sensor Error 3019: vys-cookie was not called before vys-log. Please contact support.  | Contact Adobe ClientCare.  |
|  Sensor Error 3025: Sub-request points back to itself  | Contact Adobe ClientCare.  |

**AOL Server** 

|  Event Message  | Suggested Action  |
|---|---|
|  Sensor Error 3015: ns/server/[server]/module/[module] section is missing in AOLServer config file.  | This is a configuration error. Correct as stated in error.  |
|  Sensor Error 3019: vys-cookie was not called before vys-log. Please contact support. Contact Adobe ClientCare.  | Please contact support. Contact Adobe ClientCare.  |
|  Sensor Error 3020: VisualSciencesConfig missing as first entry in [section] section in AOLServer config file.  | This is a configuration error. Correct as stated in error.  |
|  Sensor Error 3021: VisualSciencesConfig is missing a value in [section] section in AOLServer config file.  | This is a configuration error. Correct as stated in error.  |

**iPlanet and Java System Web Servers** 

|  Event Message  | Suggested Action  |
|---|---|
|  Sensor Error 3011: Init directive required. Such as Init fn=vys-init config-file=”/mypath/myfile”  | This is a configuration error. The iPlanet init directive is missing.  |
|  Sensor Error 3015: config-file is not specified in iPlanet Init directive  | This is a configuration error. The path to the configuration file was not supplied in the iPlanet Init directive.  |
|  Sensor Error 3019: vys-cookie was not called before vys-log. Please check configuration file  | vys-cookie must be specified as the first NameTrans directive for each software virtual server.  |
