---
description: The DeviceAtlas.bundle file now uses an in-memory cache to greatly improve the performance of lookups
seo-description: The DeviceAtlas.bundle file now uses an in-memory cache to greatly improve the performance of lookups
seo-title: Device Atlas with In-Memory Cache
title: Device Atlas with In-Memory Cache
uuid: 2096b9fe-c745-48a2-9f86-00f43fa1d115
---

# Device Atlas with In-Memory Cache{#device-atlas-with-in-memory-cache}

The DeviceAtlas.bundle file now uses an in-memory cache to greatly improve the performance of lookups

<!-- <a id="section_8CE52445D83247FDA180EFE4FCCDC771"></a> -->

By default, Device Atlas will cache up to 100,000 user-agents and their properties. The LRU cache is entirely self-contained inside the DeviceAtlas.bundle, so any version of the server capable of using a bundle file will automatically benefit from the increased performance as soon as the new file is loaded.

**Modifying the DeviceAtlas.cfg file**

The maximum size of the LRU cache can be configured by modifying the Cached Elements Limit parameter in the DeviceAtlas.cfg file.

Starting with the Data Workbench 6.4 release, you can override the default Cached Elements Limit of "100000" by changing its value and saving the file. The default value has been selected to be sufficient for most needs.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string: Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\ 
  
<b> Cached Elements Limit = unsigned int: 100000</b> 

```

