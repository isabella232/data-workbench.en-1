---
description: Security update for Data Workbench Report Portal.
seo-description: Security update for Data Workbench Report Portal.
seo-title: DWB Report Portal 2.1
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
---

# DWB Report Portal 2.1{#dwb-report-portal}

Security update for Data Workbench Report Portal.

**Important Security update**

The Report Portal now features stronger hashing algorithms with salting support. If you are upgrading to Report Portal 2.1, add a new Text field, PasswordSalt with field size of 20 characters in users.mdb database. This field is required to store the password salt. 
