---
description: To use Report Portal, you must install and configure a set of application server pages (ASPs) on IIS.
solution: Analytics
title: Installing the Report Portal
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
---

# Installing the Report Portal{#installing-the-report-portal}

To use Report Portal, you must install and configure a set of application server pages (ASPs) on IIS.

 **Before You Begin**

The procedures in this chapter describe how to install and configure [!DNL Report Portal]. To complete these procedures, you must:

* Have Microsoft IIS installed and know its version. 
* Know the names of the report sets whose reports are displayed by [!DNL Report Portal]. 
* Know the location of the directory in which [!DNL Report Server] saves the output for these report sets. Make certain that the IIS application server has access to this directory.

>[!NOTE]
>
>* To be viewed using [!DNL Report Portal], reports must follow specific naming conventions. Additionally, the directory into which reports are saved must follow a prescribed structure. For a description of these requirements, see [Ensuring that Your Report Sets are Compatible with Report Portal...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706). 
>
>* Passwords in report portal are now AES-256 bit compliant. If upgrading to Report Portal 2.0, increase the Field Size for Password field from 50 to 150 in the **users.mdb** database. Increasing the field size is required to accommodate passwords with updated encryption. 
>* If you are upgrading to Report Portal 2.0, increase the Field Size for the **Password** field from 50 to 150 in users.mdb database. Increasing the field size is required to accommodate passwords with updated encryption. 
>* The Report Portal now features stronger hashing algorithms with salting support. If you are upgrading to **Report Portal 2.1**, add a new Text field, *PasswordSalt* with field size of 20 characters in [!DNL users.mdb]database. This field is required to store the password salt. 
>

