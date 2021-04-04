---
description: To configure Report Portal, you must map its application files to virtual directories.
solution: Analytics
title: Map the Report Portal Pages to Virtual Directories
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
---
# Map the Report Portal Pages to Virtual Directories{#map-the-report-portal-pages-to-virtual-directories}

To configure Report Portal, you must map its application files to virtual directories.

A virtual directory defines the address that browser clients use to locate a physical resource on the IIS application server. To access [!DNL Report Portal], clients point their browsers to the virtual directory that you assign to the portal.

The name of the virtual directory that you assign to [!DNL Report Portal] must match the name that you used for the VSVirtualPortalName folder in Step 3 of the previous section. For example, if you want to use “Portal” as the name of your [!DNL Report Portal], you must map the portal’s files to a virtual directory named “Portal.” The following example shows the URI that clients would use to access a [!DNL Report Portal] assigned to the virtual directory [!DNL VisualReportPortal] on a server called myWebServer:

[!DNL http://myWebServer/VisualReportPortal]

The following procedures describe how to map [!DNL Report Portal] to a virtual directory on IIS 5.0, 6.0, and 7.0 or higher.

Follow the set of procedures for the version of IIS that you are using:

* [Mapping Report Portal to a Virtual Directory (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08) 
* [Mapping Report Portal to a Virtual Directory (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74) 
* \ [Edit the Session Configuration File](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
