---
description: The DeviceAtlas JSON file will now be distributed in a .bundle file (a renamed .tar.gz) along with DeviceAtlas.dll and DeviceAtlas64.dll files.
solution: Analytics
title: DeviceAtlas Distribution
topic: Data workbench
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
---
# DeviceAtlas Distribution{#deviceatlas-distribution}

The DeviceAtlas JSON file will now be distributed in a .bundle file (a renamed .tar.gz) along with DeviceAtlas.dll and DeviceAtlas64.dll files.

When the administrator upgrades the Insight Server to version 6.0, the DeviceAtlas.bundle file is included with the upgrade package in the Software and Docs profile (softdocs profile) located at:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

The DeviceAtlas.bundle file is extracted to [!DNL Server\Lookups\DeviceAtlas].

The DeviceAtlas.bundle file should be placed in a directory that is synchronized to the DPUs, and the DeviceAtlas.cfg file corresponding to the new DeviceAtlasComponent should be placed in the "Components for Processing Servers" directory on the synchronization master. When the DeviceAtlas.bundle file is changed, the very next DeviceAtlas lookup call will get results based on the updated API and/or JSON file.

## Modify the Transformation.cfg file {#section-394823348f5740028666e62e2bd42754}

The DeviceAtlas Transformations will no longer need to specify the path to the JSON file. Any previous DeviceAtlasTransformation that is defined in the transformation.cfg file should no longer include the File parameter that points to the obfuscated JSON file.

This example Transformation.cfg file shows the File argument that should be deleted to avoid confusion. (Leaving it there will not cause harm, but only potential confusion because it will be ignored.)

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  

```

## Modify the DeviceAtlas.cfg file {#section-10b43705a6c846fd9ec54ea6be249f88}

This is an example of the [!DNL component] argument required in the DeviceAtlas.cfg file.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

This DeviceAtlas.bundle file will be treated just like a configuration file from the perspective of the Profile Synchronization feature. In addition, the JSON data and DLL will be used at the Component level rather than at the individual Transformation level.

A new DeviceAtlasComponent, upon startup, finds the .bundle conglomeration, de-obfuscates the JSON file into memory, extracts the files into a temporary directory, and loads the appropriate DLL for the running platform. This component also monitors changes to the bundle file, and reloads the DLL and .cfg file automatically if it changes.

## Running DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Proper configuration makes a big difference in the time required for transformation. The transformation can be configured to run only once per visitor per session to allow DeviceAtlas to speed up the process.

**If deployed using Log Processing.cfg**:

Run the transformations twice.

1. Look up only the [!DNL mobile id] field, then 
1. Create conditions to ignore the [!DNL mobile id] and then look up the rest of the fields.

**If deployed using Transformation.cfg**:

Deploy as in Step 1 in Log Processing above, or use cross-rows to support a conditional setting.

* Cross-Rows—Grab the previous session key. Then identify if the current session key is different from the one found with cross-rows. If so, then the DeviceAtlas transformation will only run on one record per session.
