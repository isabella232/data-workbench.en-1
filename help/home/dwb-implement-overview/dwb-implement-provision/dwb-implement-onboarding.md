---
description: Follow these steps to start the onboarding process for Adobe Data Workbench (DWB), a component of Adobe Analytics Premium (AAP).
seo-description: Follow these steps to start the onboarding process for Adobe Data Workbench (DWB), a component of Adobe Analytics Premium (AAP).
seo-title: Basic Onboarding Instructions for DWB Managed Services
title: Basic Onboarding Instructions for DWB Managed Services
uuid: b27e9463-bb00-4e43-9ab5-d0fee35e70e3
index: y
internal: n
snippet: y
---

# Basic Onboarding Instructions for DWB Managed Services{#basic-onboarding-instructions-for-dwb-managed-services}

Follow these steps to start the onboarding process for Adobe Data Workbench (DWB), a component of Adobe Analytics Premium (AAP).

These onboarding instructions are for customers implementing Data Workbench with a single report suite using Adobe managed services without consulting services. If you are a new AAP customer implementing DWB, the Adobe Onboarding team will be your initial contact. If upgrading from Adobe Analytics standard or from an earlier version of DWB, an Adobe Customer Success Manager will assist you.

## Onboarding Info: What We Need from You {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe will contact you to:

* Identify a Primary User for DWB to generate a certificate specifically for that user on the network directory. The primary user will also act as the point person to interact with Adobe Customer Care. 
* Identify the report suite to be loaded into DWB.

The Adobe Digital Marketing teams will then take your information to create profiles, set accounts, and deliver a configuration file for DWB.

**Adobe Onboarding Tasks**

* Adobe Customer Care creates a DWB licensed account. Adobe Customer Care generates a DWB certificate for the primary user. 
* Adobe Customer Care defines the primary user as a “supported user,” the person identified for supported calls and problem resolution. 
* Adobe Customer Care loads software package to the DWB license and software portal (SoftDocs/Software and Docs profile) to be downloaded to your organization. 
* Adobe TechOps team prepares the Production and Development environments and their profiles (per contract) for DWB. 
* Adobe TechOps team configures data feeds and profile management scripts. 
* Adobe TechOps team creates and sends the DWB configuration file (Insight.cfg) to the Adobe Onboarding team responsible for on-boarding tasks associated with your organization.

After customizing your data feeds and generating credentials, certificates, and a profile configuration, the Adobe Customer Care will send your configuration file and credentials to take the next step.

## Access your Custom Install Files {#section-26962bf57fef435dbd1c5486d4b6f688}

You will receive these setup files from Adobe Customer Care to install the DWB Workstation on your client computer.

* Your custom DWB configuration file (Insight.cfg)

  This configuration file on the client computer will include connections to your managed DWB servers. 

* Login credentials for the Licensing Portal to download the DWB Setup Wizard and required certificate (.pem file) with the name of your primary user.

**Download additional setup files**

1. Browse to: license.visualsciences.com to download you license certificate and the DWB Setup Wizard executable. 
1. Enter your Organization (Account Name), the name of the primary User,&nbsp;and the Password that you received from Adobe Customer Care, then click&nbsp;login.

   >[!NOTE]
   >
   >Your browser might prompt you to present a digital certificate at this point. If it does, click&nbsp;Cancel&nbsp;to dismiss the dialog box.

1. Locate the certificate issued for your instance of Adobe&nbsp;Data Workbench&nbsp;(<PrimaryUser>.pem) in the Downloads section and download. 
1. Locate Standard Client Installer in the Downloads section to download the DWB Setup Wizard (InsightSetup-x.xx.exe file). 
1. After receiving and downloading files from Adobe Customer Care, run the DWB Setup Wizard to install the workstation software to your client computer.

>[!NOTE]
>
>The DWB Setup Wizard will walk you through installation of the DWB client workstation and help locate the Insight.cfg and <PrimaryUser>.pem files to place in the required folders. The Insight.cfg file resides with the Insight.exe file in your installed client workstation. The <PrimaryUser>.pem file resides in the Certificates folder with the trust_ca_cert.pem file. All certificate and configuration files must be present for&nbsp;DWB to function.

For additional information, see the [DWB Setup Wizard](https://marketing.adobe.com/resources/help/en_US/insight/install/dwb_client_installer.html).

## Connection to your DWB Servers {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Your managed servers are identified in the Insight.cfg file that you receive from Adobe Customer Care and resides on your client workstation. Adobe TechOps will set up your servers and Adobe Customer Care will add references to these managed servers and profiles to the Insight.cfg file before sending it to you. (The Configure connections to server in step 12 of the DWB Setup Wizard documentation will be completed.)

>[!NOTE]
>
>In the Workstation Configuration workspace on the DWB client workstation, you will be able to see your connected servers and profiles.

****

**Adobe Managed Services**

• Adobe TechOps manages the infrastructure including network, data center, servers, and storage. Infrastructure monitoring and response to alerts occurs on a 24x7 basis for alerts requiring TechOps action. For other alerts, TechOps will notify Adobe Customer Care to coordinate with you.

• Adobe TechOps will perform maintenance and firmware updates for your managed servers. For maintenance causing downtime, you will receive maintenance window notifications from Customer Care at least two weeks in advance. Adobe TechOps will address immediate needs as quickly as possible. Notification will depend on urgency and will be resolved once the schedule is known.

• Adobe TechOps sets up a scheduled task to automatically manage data. Analytic feed data is moved into DWB for processing and transformation every evening beginning at 21:00 report suite time.

• Adobe TechOps will process other Adobe Managed Services include data backups, FTP accounts, data archiving, and data transfer when necessary.

• Adobe TechOps will configure the primary production cluster to contain three months of rolling data to be reset and reprocessed monthly. Updates to lookups (Geography, DeviceAtlas, Standard Classifications) will also occur as part of the reprocessing task. By default, the task runs on the first Friday of each month. If necessary, the schedule can be modified by Customer Care.

For additional information contact Adobe Customer Care at [dataworkbench@adobe.com](dataworkbench@adobe.com) or call 800.497.0335. 
