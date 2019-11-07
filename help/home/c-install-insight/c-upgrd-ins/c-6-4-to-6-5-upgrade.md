---
description: Follow these steps to upgrade to Data Workbench v6.5.
title: Upgrading 6.4 to 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
---

# Upgrading 6.4 to 6.5{#upgrading-to}

Follow these steps to upgrade to Data Workbench v6.5.

## Upgrade Requirements and Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Follow these requirements and recommendations when upgrading to Data Workbench 6.5.

* Changes in the **[!DNL Components for Processing Servers\Communications.cfg]** file require you to update this file for the DWB 6.5 release. The *SourceListServer*, *SegmentExportServer*, and *NormalizeServer* entries were removed. ( DPU's should not be running *sourcelist*, *segment export*, or *normalize servers*. ) 

* Correlation Chord, Correlation Matrix, Association Chord, Association Matrix, Propensity Score and Best Fit Attribution visualizations are now multi-pass visualizations.

  When there are more than one multi-pass visualizations in a workspace, Report Server will fail to generate reports by default with the error:

  ```
  Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
  ```

  Avoid this error by updating your [!DNL ReportServer.cfg] file or add this line to your existing file in the *Reporting* section. 

  ```
  Max Multipass Per Slice = int: n
  ```

  where n is the maximum number of multi-pass visualizations supported by Report Server in a workspace.

