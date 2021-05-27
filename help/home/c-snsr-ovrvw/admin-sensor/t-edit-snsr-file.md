---
description: The Sensor configuration file, txlogd.conf, contains parameters that Sensor uses to establish a connection with the data workbench server.
title: Editing the Sensor txlogd.conf File
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
---
# Editing the Sensor txlogd.conf File{#editing-the-sensor-txlogd-conf-file}

The Sensor configuration file, txlogd.conf, contains parameters that Sensor uses to establish a connection with the data workbench server.

 These parameters include the server’s address, port number, and communication protocol (HTTP or HTTPS). The configuration file also contains log-content filtering options and controlled experiment information. Controlled experiments enable site designers to perform experiments to test content or design changes on a subset of all site visitors.

When changing other [!DNL txlogd.conf] parameters, such as the IP address of the [!DNL data workbench server] or the name of the [!DNL Sensor], you may be able to simply replace [!DNL txlogd.conf] with the updated version and [!DNL Sensor] will pick up the changes automatically. On some systems, you may not be able to edit or replace the file without stopping either the web server or the transmitter process.

**To open and edit txlogd.conf** 

1. Browse to the [!DNL Sensor] installation directory and open the [!DNL txlogd.conf] file in a text editor.
1. Edit the file as necessary.
1. Save and close the file.

    * The location of the controlled experiment configuration file (defined by the ExpFile parameter in the [!DNL txlogd.conf] file) should be in a directory on the web server that is accessible to your web content developers or controlled by your content management system. 
    * The value in the ExpCookieURL parameter is a virtual page that is used to test websites. A user visiting that page will be given a new tracking ID.

For more information about working with [!DNL txlogd.conf], please contact Adobe Consulting Services.
