---
description: Adobe Data Workbench provides tools and processes to ready your data to comply with the General Data Protection Regulations (GDPR).
solution: Analytics
title: Data Workbench Support for GDPR
topic: Data workbench
exl-id: fdc43567-0c57-4851-9073-e295258a8074
---
# Data Workbench Support for GDPR

Adobe Data Workbench provides tools and processes to ready your data to comply with the [!DNL General Data Protection Regulations] (GDPR).

Like all Adobe Analytics solutions, Data Workbench provides support for GDPR by providing cleansing, deleting, and labeling of analytic variables when processing the Adobe Analytics' data feed. To support GDPR implementations, Adobe lets you set up processes for GDPR in accordance with your company’s permissions as established in your agreement with Adobe. See [Adobe Analytics and GDPR for additional information](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

The GDPR regulation identifies the roles and obligations of the different parties responsible for GDPR enablement (see [GDPR and Your Business](https://www.adobe.com/privacy/general-data-protection-regulation.html)).

* Your organization acts as the **data controller** to determine the context and retention of personal data based on your needs and constraints. Adobe then processes and stores this data on your behalf.
* Adobe acts as the **data processor** to provide the software and services to implement GDPR requirements based on your agreement with Adobe.
* After integration of Data Workbench with the GDPR service and according to GDPR standards, visitors to a site (the **data subjects**) can exercise their "right to be forgotten" by Adobe, the data processor. To accomplish the right to be forgotten, you as the data controller can upload challenged visitor IDs to Adobe from a UI or API. See the [Adobe Analytics GDPR Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) documentation for more information, including the [submit access and delete requests](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) section.

>[!NOTE]
>
>For other data sources, your organization will be responsible for cleaning up challenged visitor IDs from other log sources, such as the CRM, POS, IVR, and other raw data sources. Custom-scoped services packages will be available to provide support for organizations by _providing a full replacement set of files for each data source_ that ongoing service retainers are required to support or maintain.

## Upgrading DWB for GDPR Implementation

Consulting will advise you on the appropriate services package to bring existing implementations into compliance. Please contact your Customer Success Manager (CSM) for additional information.

If required:

* [Upgrade to the latest version](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) of Data Workbench. For the highest security, new certificates and security features were added in the DWB 6.7 releases that are required for GDPR integration.
* If using legacy TSV Analytics event logs, upgrade to the [Avro data feed](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* If using a legacy UCP (Unified Customer Process) with Transform to update existing logs, upgrade to the current process. The updated process directly generates a master lookup file for mapping visitor IDs across sources.
* Standardize data flow to accommodate the GDPR service.
* Establish a custom-scoped services package to manage other log sources such as CRM, POS, IVR, and other raw data sources.
* Confirm default data retention period of 25 months or more in the Analytics contract.
