---
description: Steps to upgrade the Transform folder.
seo-description: Steps to upgrade the Transform folder.
seo-title: Upgrading Transform
solution: Insight
title: Upgrading Transform
uuid: 20b84034-1ee7-4f5d-89b9-150cbaa17a45
index: y
internal: n
snippet: y
---

# Upgrading Transform{#upgrading-transform}

Steps to upgrade the Transform folder.

1. Open the [!DNL .zip] file for the [!DNL Insight Server] release package, and open the [!DNL Profiles] folder within that [!DNL .zip] file.
1. Copy the [!DNL Transform] folder to the [!DNL Profiles] folder in your [!DNL Insight Server] installation directory. Doing this overwrites the existing [!DNL Transform] folder.
1. For each profile that inherits the [!DNL Transform] profile, confirm that the [!DNL profile.cfg] file has a “Transform” entry in the Directories vector.
Data reprocessing begins after synchronization of the profile. 
