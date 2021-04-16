---
description: To specify the profiles that you want to be available in Report Portal, you must configure the profiles.xml file.
title: Edit the Profiles.xml File
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
---
# Edit the Profiles.xml File{#edit-the-profiles-xml-file}

To specify the profiles that you want to be available in Report Portal, you must configure the profiles.xml file.

The [!DNL profiles.xml] file resides in the folder you have designated for output. By default it resides in the \*PortalName*\PortalFiles\Output folder.

**To add profile names to the profiles.xml file** 

1. On the machine where IIS is running, open the [!DNL profiles.xml] file in a text editor such as Notepad.
1. Add a profile element and tag for each [!DNL Profile] in your portal, as in the following example:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Save and close the file.
