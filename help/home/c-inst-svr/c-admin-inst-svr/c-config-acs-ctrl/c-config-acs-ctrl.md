---
description: The Access Control configuration file, Access Control.cfg, defines the access control groups by which Insight Server grants permissions to files based on the attributes (OU, CN, and so forth) of the incoming connection’s certificate.
solution: Insight
title: Configuring Access Control
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
---

# Configuring Access Control{#configuring-access-control}

The Access Control configuration file, Access Control.cfg, defines the access control groups by which Insight Server grants permissions to files based on the attributes (OU, CN, and so forth) of the incoming connection’s certificate.

 **Recommended Frequency:** As needed

[!DNL Insight Server] provides configurable access control groups to manage the security of connections to [!DNL Insight Server]. Access control groups identify users that are permitted to perform administrative functions through [!DNL Insight].

If you need to provide access to new users or new machines, such as when adding a machine to an [!DNL Insight Server] cluster, you simply edit the Access Control configuration file. 
