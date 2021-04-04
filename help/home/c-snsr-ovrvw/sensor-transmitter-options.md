---
description: Information about Sensor transmitter start-up commands for UNIX and for Windows.
title: Sensor Transmitter Command-Line Options
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
---
# Sensor Transmitter Command-Line Options{#sensor-transmitter-command-line-options}

Information about Sensor transmitter start-up commands for UNIX and for Windows.

## Start-up Command for UNIX {#section-e8e7a6e62971499ba5f633d896590949}

To start the Sensor transmitter on a UNIX stem, you use the following command:

```
txlogd -f configFileName
```

where configFileName is the fully qualified name of the transmitter configuration file (txlogd.conf).

By default, the transmitter runs as a background process (a daemon) and writes operational messages to syslog.

The following is a complete list of the command-line switches for txlogd: 

|  Switch  | Description  |
|---|---|
|  -f  | Specifies the fully qualified name of the configuration file (txlogd.conf). If you do not specify this switch, the transmitter looks for txlogd.conf in the current directory.  |
|  -n  | Starts the transmitter in interactive mode (not as a background process).  |
|  -i  | Starts the transmitter in interactive mode and directs debug output to stdout.  |
|  -d  | Starts the transmitter as a background process and directs debug output to txlogd-debug.log in the current directory.  |
|  -c  | Starts the transmitter and creates the disk queue file if it doesn’t exist. If the disk queue already exists, this parameter is ignored.  |
|  -x  | Starts the transmitter and causes it to exit after it transmits the last packet in the disk queue. You can use this option to drain the queue in preparation for an administrative operation such as creating a new queue file.  |

## Start-up Command for Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

To start Sensor and register it as a service on a Windows system, you use the following command: 

```
txlog /regserver
```
