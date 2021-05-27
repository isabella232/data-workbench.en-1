---
description: For all languages, Report Server 6.0 and later requires the "insight.zbin" file copied to the Report Server root folder.
title: Update Report Server with a language file (.zbin file)
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
---
# Update Report Server with a language file (.zbin file){#update-report-server-with-a-language-file-zbin-file}

For all languages, Report Server 6.0 and later requires the "insight.zbin" file copied to the Report Server root folder.

 Update the Report Server language files:

1. Add the renamed "insight.zbin" file to the root ReportServer directory. 
1. The Report Server configuration file (reportserver.cfg) requires font settings for double-byte languages. For example, Chinese requires the addition of fonts using SimSun: 

   ```
   <b>Report Server.cfg - Add Fonts</b> 
    
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. A parameter for Report Server 6.0 needs to be passed in the command line for localization, for example: 

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >If a locale is not specified, then the Report Server defaults to English.

   Follow the steps to launch the ReportServer as a service with the Locale parameters:

    1. Launch a Command Prompt as an Administrator. 
    1. Navigate to the ReportServer install folder. 
    1. Type the following command to start the service:

        * For English: [!DNL ReportServer.exe -RegServer -Locale -en-us] 
        * For Chinese: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. To verify if the ReportServer is running with the correct parameters:

    1. Open up Windows Service Manager. 
    1. Right-click [!DNL Adobe Insight Report Server - Properties].

   The path to executable will contain the parameters:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
