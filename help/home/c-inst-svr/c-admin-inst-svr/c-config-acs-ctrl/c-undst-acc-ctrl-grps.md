---
description: Five pre-built access control groups are available, but you can create and manage additional groups as required.
seo-description: Five pre-built access control groups are available, but you can create and manage additional groups as required.
seo-title: Understanding Access Control Groups
solution: Insight
title: Understanding Access Control Groups
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
---

# Understanding Access Control Groups{#understanding-access-control-groups}

Five pre-built access control groups are available, but you can create and manage additional groups as required.

 You may define the members of each access control group, as well as the directories to which each group has Read-Only or Read-Write access.

The pre-defined groups are defined as follows:

|  Group  | Description  |
|---|---|
|  Administrators  | Allows access to all directories and files. The default IP address is 127.0.0.1 (local host).  |
|  Sensors  |Allows access to only those files used by [!DNL Sensor] to transmit data.  |
|  Users  |Allows read-only access to the elements required for an [!DNL Insight] user to perform basic analysis tasks.  |
|  Power Users  |Allows read-only access to the elements required for an [!DNL Insight] user to perform basic analysis tasks, plus read and write access to the [!DNL Profiles] folder for modifying profiles.  |
|  Cluster Servers  |Allows access to [!DNL Insight Servers] that are designated as cluster servers.  |
|  Report Servers  |Allows access to [!DNL Report] machines that connect to the [!DNL Insight Server].  |

Members of an access control group are defined using their IP addresses or SSL certificate information.

If an SSL certificate is not available, an IP address may be used to define a group member. The typical installation of [!DNL Insight] includes an SSL certificate, while the use of certificates for [!DNL Sensor(s)] is optional. For [!DNL Insight Server], Cluster Servers are defined using IP addresses instead of SSL certificates.

The following codes can be used to define group members:

|  Access Types Code  | Definition  |
|---|---|
|  O  | Organization  |
|  CN  | Common Name  |
|  L  | Locality  |
|  ST  | State or Province  |
|  C  | Country  |
|  OU  | Organizational Unit  |
|  Email  | Email address  |

