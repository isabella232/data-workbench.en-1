---
description: This section is a quick guide giving you the minimum steps required to set up and schedule scripts to weekly reprocess your log files. This can be used as reference guide to set up or modify your profiles.
title: Scripting to Weekly Reprocess
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
---
# Scripting to Weekly Reprocess{#scripting-to-weekly-reprocess}

This section is a quick guide giving you the minimum steps required to set up and schedule scripts to weekly reprocess your log files. This can be used as reference guide to set up or modify your profiles.

## What is Reprocess {#section-7e335aacc199488592e78a835e2649fe}

Loading the data to DWB based on changes in data sources, offline data sources, or time period. The script will reprocess the start date parameter in *Log Processing.cfg* file.

## Prerequisites {#section-804acce5df4942469c9313535627038a}

Report Suite ID, Number of month data should be available in DWB. The Perl64 folder should be available in your C:\ drive.

## Reprocess Logs {#section-565d3e1f0df14127a97d9beecd14f02f}

Provide above details (prerequisites) in windows command script *Reprocess.bat* available at folder *\scripts\Log Processing* at Main FSU server.

This script will internally call two client specific scripts: One to reprocess the data and other for email alert. These two scripts are also available in the *\scripts\Log Processing* folder.

The script will change reprocess parameters in the *Log Processing.cfg* file.

## Rolling Window for Logs {#section-ed5f44d890b34523ab33da7aa0ae3990}

Provide details (prerequisites) in windows command script *logprocessingdate.bat* available at folder *\scripts\Scripository* on the maing FSU server. This script will internally call two client specific scripts: One to setting up start date of logs and another for email alerts. These two scripts are also available in* \scripts\Scripository*

Provide Report suite id and number of months in the* logprocessingdate.bat* file.

The script will change the start date parameter in *Log Processing.cfg*.

>[!NOTE]
>
>If the *Scripository* folder is not available, follow the below process to copy the *Scripository* folder and make changes in above files using details specific for customer. And provide your email address to get an alert in case of any error.

## Scheduling Scripts {#section-063cf0c755dc47d28d60947d8d43d0e9}

Follow these steps to schedule the scripts in the Windows task scheduler.

1. Schedule the script in Windows' task scheduler.

    * Open Task Scheduler: Right click on the **Task Scheduler Library** and click **Create Task**. 
    
    * In the **General** tab provide a task name and select **Options**. 
    
    * Under the **Triggers** tab, click **New** and a new window will open. 
    
    * Under the **Actions** tab, click **New** and a new window will open. Then provide script details and other options. (Start in will have a path where script is placed).

1. Validation: Right click and run the job and verify changes in the *Log processing.cfg* file. An email will be sent to the email id provided in the script.
