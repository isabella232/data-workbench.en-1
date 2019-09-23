---
description: Considerations to keep in mind when working with DPU and FSU networks.
seo-description: Considerations to keep in mind when working with DPU and FSU networks.
seo-title: DPU and FSU Network Issues
solution: Analytics
title: DPU and FSU Network Issues
uuid: 569d44ea-4423-48b1-b098-64c3dfa7ba29
---

# DPU and FSU Network Issues{#dpu-and-fsu-network-issues}

Considerations to keep in mind when working with DPU and FSU networks.

* For networked log file distribution, any networked storage system hosting log files needs to provide at least 10MB per DPU of sustained bandwidth. 
* The DPU, FSU, and Data Workbench inter-communicate bi-directionally via HTTP or HTTPS on port 80 or 443 (by default; ports can be alternatively configured). 
* Data Workbench [!DNL Sensor(s)] must be able to connect (one-way) to the servers. 
* To allow the DPU to send alert messages via SMTP, it must be able to contact the configured SMTP server. 
* Adobe recommends that FSUs and DPUs be given network names such as FSU01.CLIENT.COM to avoid reconfiguration if the case of an IP-address change.

