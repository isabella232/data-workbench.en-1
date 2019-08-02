---
description: Dataset configuration refers to the process of editing the configuration files whose parameters provide the rules for dataset construction.
seo-description: Dataset configuration refers to the process of editing the configuration files whose parameters provide the rules for dataset construction.
seo-title: Understanding Dataset Configuration
solution: Analytics
title: Understanding Dataset Configuration
topic: Data workbench
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
index: y
internal: n
snippet: y
---

# Understanding Dataset Configuration{#understanding-dataset-configuration}

Dataset configuration refers to the process of editing the configuration files whose parameters provide the rules for dataset construction.

 The constructed dataset physically resides in the [!DNL temp.db] file stored on the data workbench server computer, but the configuration files for the dataset reside within a directory for a profile. A profile contains a set of configuration files that construct a dataset (including its extended dimensions) for a specific analysis purpose. In addition, a profile contains the definitions of entities such as metrics, derived dimensions, workspaces, reports, and visualizations that enable analysts to interact with the dataset and obtain information from it.

The profile whose dataset configuration files you are editing is referred to as your dataset profile. A dataset profile references multiple inherited profiles, which can be any profiles that you create and maintain so that you can configure your Adobe application to best fit your analysis needs. A dataset profile also may reference internal profiles that are provided with your Adobe application to form the basis for all of the functionality available in your application.

For more information about the different types of profiles that are available with Adobe applications, see the *Data Workbench User Guide*.

<!--
c_req_config_files.xml
-->

A dataset profile for any Adobe application must contain the following configuration files on the Insight Server machine:

* **Profile.cfg:** Lists the inherited profiles and processing servers for the profile. Processing servers are the Insight Server DPUs that process the data for the profile. If you have installed an Insight Server cluster, you can specify multiple Insight Server computers to run a single profile.

  For instructions to add inherited profiles to a dataset profile's [!DNL Profile.cfg] file, see the *Server Products Installation and Administration Guide*. For information about installing an Insight Server cluster or configuring a dataset profile to run on an Insight Server cluster, see the *Server Products Installation and Administration Guide*. 

* **Dataset\Log Processing.cfg: **Controls the log processing phase of the dataset construction process. See [Log Processing](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). For more information about the [!DNL Log Processing.cfg] file, see [Log Processing Configuration File](../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-proc-config-file.md#concept-20e3148be47841a1b33ae55d23667d33). 

* **Dataset\Transformation.cfg:** Controls the transformation phase of the dataset construction process. See [Transformation](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). The [!DNL Transformation.cfg] file typically configures the dataset for profile-specific analysis. For more information about the [!DNL Transformation.cfg] file, see [Transformation Configuration File](../../home/c-dataset-const-proc/c-trans-config-file/c-trans-config-file.md#concept-cfe9e04d11fd43d980cec36c3c7af211). 

* **Dataset Include Files:** A [!DNL dataset include] file contains a subset of the parameters contained in the [!DNL Log Processing.cfg] or [!DNL Transformation.cfg] file for the dataset profile but is stored and managed within an inherited profile. [!DNL Dataset include] files supplement the main dataset configuration files. For more information, see [Dataset Include Files](../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df).

The dataset profile provided to you during the implementation of your Adobe application contains a set of dataset configuration files that you can open, edit, and save using the [!DNL Profile Manager].

For information about the [!DNL Profile Manager], see the *Insight User Guide*.

<!--
c_addl_config_files.xml
-->

Although not required for all datasets, these files enable you to control other aspects of the dataset construction process:

* **Log Processing Mode.cfg:** The [!DNL Log Processing Mode.cfg] file lets you pause processing of data into a dataset, specify offline sources, or specify the frequency at which the data workbench server saves its state files. See [Additional Configuration Files](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004). 

* **Server.cfg:** The [!DNL Server.cfg] file specifies the default data cache size (in bytes) for data workbench machines that connect to the data workbench server. See [Additional Configuration Files](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004). 

* **Transform.cfg and Transform Mode.cfg:** These files are available only if you have licensed the data transformation functionality to use with your Adobe application. The [!DNL Transform.cfg] file contains the parameters that define the log sources and data transformations for transformation functionality. The transformations that you define manipulate the source data and output it into a format that you specify. The [!DNL Insight Transform Mode.cfg] file enables you to pause processing of data into a dataset, specify offline sources, or specify the frequency at which the Insight Server running transformation functionality saves its state files. See [Transform Functionality](../../home/c-dataset-const-proc/c-transf-func/c-transf-func.md#concept-d845aa29494f4a93984b5698a82dde8d).

<!--
c_next_steps.xml
-->

For information about specific dataset configuration tasks, use the table below to locate and read about the tasks of interest of you:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> If you would like to... </th> 
   <th colname="col2" class="entry"> See... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Define log sources </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea" format="dita" scope="local"> Log Sources </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Determine which log entries enter the dataset during log processing </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d" format="dita" scope="local"> Data Filters</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934" format="dita" scope="local"> Log Entry Condition</a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Enable the splitting of tracking IDs with large amounts of event data </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf" format="dita" scope="local"> Key Splitting</a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Configure an Insight Server to run as a file server unit </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d" format="dita" scope="local"> Configuring an Insight Server File Server Unit </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Configure an Insight Server to run as a centralized normalization server </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d" format="dita" scope="local"> Configuring an Insight Server File Server Unit </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Set the time zone to be used for creating time dimensions and making time conversions </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956" format="dita" scope="local"> Time Zones </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Make minor changes to the dataset configuration files included with the internal profiles provided by Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077" format="dita" scope="local"> Editing Existing Dataset Include Files </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Specify new fields of data to be passed from log processing to transformation </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e" format="dita" scope="local"> Creating New Dataset Include Files </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab" format="dita" scope="local"> Log Processing Dataset Include Files </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Define transformations </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-data-trans.md#concept-99c6f5e6e5194adb9e98afdc0e91cf38" format="dita" scope="local"> Data Transformations </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e" format="dita" scope="local"> Creating New Dataset Include Files </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace" format="dita" scope="local"> Transformation Dataset Include Files </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Create extended dimensions </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-ex-dim.md#concept-79b9e2b3f5794833b8b73b003f06ddca" format="dita" scope="local"> Extended Dimensions </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e" format="dita" scope="local"> Creating New Dataset Include Files </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace" format="dita" scope="local"> Transformation Dataset Include Files </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Define parameters to use throughout log processing or transformation </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50" format="dita" scope="local"> Defining Parameters in Dataset Include Files </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Learn about the Insight interfaces that enable you to monitor or manage your dataset </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab" format="dita" scope="local"> Working With Dataset Configuration Interfaces </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Hide certain extended dimensions so they do not show on the dimension menu in Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff" format="dita" scope="local"> Hiding Dataset Components </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Override certain dataset configuration files in a profile that you cannot or do not want to modify </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff" format="dita" scope="local"> Hiding Dataset Components </a> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Reprocess your dataset </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823" format="dita" scope="local"> Reprocessing and Retransformation </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

