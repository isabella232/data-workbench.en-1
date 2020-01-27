---
description: Use Workstation to manage your Data Workbench users.
title: Self-provisioning of users
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
---

# Self-provisioning of users{#self-provisioning-of-users}

Use Workstation to manage your Data Workbench users.

You can use Workstation to connect to the Data Workbench Server by setting up the required certificate from Adobe. This certificate aids in both SSL communication and authorization to use the licensed resources and features. In certificate-based authentication, you need to acquire and setup multiple certificates for using the Workstation on multiple machines. Also, user provisioning and entitlements are managed by Adobe and you must contact Adobe for new certificates or certificate revocation.

Starting in DWB 6.7, the Workstation supports user authentication through username and password.

While the certificate-based authentication/authorization will still work for your setup, it is highly recommended to migrate to the newer credentials-based authentication. In the newer approach, your Workstation users authenticate themselves through the Adobe Identity Management System (IMS). Before they can use the Workstation, they need to be given access to the features through the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) by the administrator of the organization.

The new authentication and user provisioning model helps in:

* Self-provisioning of users and groups through Admin Console. You don’t have to contact Adobe to add, remove, or modify license entitlements for users. 
* Accessing Workstation from multiple machines without losing the configuration state by logging in using credentials. The local cache is deleted on log out, the current profile is closed, and Configuration profile becomes active.

## Getting started

Before you begin, contact Adobe to add your organization in the Admin Console. Depending on the services you have purchased, Adobe will provision the organization for you. For example, organizations can have access to the Attribution service or Beta builds, or both. Once an organization is configured, the organization administrator can add users and groups. See [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) in Experience Cloud for more information. The organization administrator can also configure usage restrictions for different users depending on their roles. For example, non-pre-release users do not need access to the Beta builds.

Each provisioned user added to this organization through the Admin Console will have access to use the Data Workbench. The sub-services can only be enabled or disabled for each user depending on their product access. When a user is upgraded from certificate to IMS, all local data will be copied to the new IMS user directory.

>[!NOTE]
>
>A session lasts 6 hours on Server and 23 hours on Client unless the access token is refreshed. When the token is refreshed, you can use Client without logging in again.

At least one Product Level Configuration needs to be created in Admin Console by the administrator before giving access to any user.

The boolean flag **Use IMS** can be added to [!DNL Insight.cfg] to fallback to certificate mode. For information on configuring Access Control for IMS users, see [Updating the Access Control File](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Conflict resolution

When a user is logged on to multiple machines with same IMS account on the same profile, and is in offline mode on one of the machines, a `.conflict` may form and a pop-up window will inform you. This occurs when there is a difference in content with any files (workspaces, dimensions, filters, etc.) synced on both machines in [!DNL User\Profile\] on server and client . A backup will be created in the `.conflict` file and no data will be lost. A boolean flag in [!DNL Insight.cfg] gives you the ability to disable this conflict pop-up.

Flag: Conflict Notifications

This is applicable for workspaces, metrics, dimension, etc. in User Folder. 
