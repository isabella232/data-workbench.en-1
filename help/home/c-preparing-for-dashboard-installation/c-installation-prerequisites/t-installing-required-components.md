---
description: Steps to install the required Microsoft components.
solution: Analytics
title: Installing Required Components
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
---

# Installing Required Components{#installing-required-components}

Steps to install the required Microsoft components.

1. Install Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >This must be installed only after installing and configuring the IIS Web Role.

1. Follow the wizard and choose defaults where prompted to complete the installation.
1. Once installed, verify that the ASP.NET v.4.0 application pool was added within the **[!UICONTROL Application Pools]** listing in IIS.
1. Install the Microsoft SQL Server Database.

   Use any version of SQL Server 2008 or 2008 R2 (Express is supported) with Management Tools (Adobe recommends SQL Server 2008 R2 SP1 - Express Edition). 1. For a generic install without existing SQL Server instances running ahead of time, please select the **[!UICONTROL Default Instance]** option on the **[!UICONTROL Instance Configuration]** screen.
1. For the rest of the configuration options, follow the wizard and choose defaults when prompted to complete the installation.
1. Install Microsoft Web Deploy v2.0.

   For most installations, the **[!UICONTROL Typical]** installation is fine. If, however, you are planning to perform remote deployments, you will need to do a full install (choose **[!UICONTROL Complete]**).

   Once all prerequisites are properly installed, you are ready to prepare the data workbench servers to communicate with the dashboard. 
