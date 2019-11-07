---
description: Instructions for adding the visual_sciences.dll to the Tomcat java library path.
title: Modify the Java Library Path
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
---

# Modify the Java Library Path{#modify-the-java-library-path}

Instructions for adding the visual_sciences.dll to the Tomcat java library path.

1. On your Windows server, navigate to Tomcat installation directory. (Tomcat > bin) 
1. Under bin folder, run Tomcat9w.exe (common daemon service manager).

In the Java tab, under Java options, add a new line:

```
-Djava.library.path=C:\Sensor directory
```

Where C:\Sensor directory is the directory containing the visual_sciences.dll file. 
