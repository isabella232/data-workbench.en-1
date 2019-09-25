---
description: The Transformation Dataset Include file for an inherited profile contains parameters associated with the transformation phase of dataset construction.
seo-description: The Transformation Dataset Include file for an inherited profile contains parameters associated with the transformation phase of dataset construction.
seo-title: Transformation Dataset Include Files
solution: Analytics
title: Transformation Dataset Include Files
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
---

# Transformation Dataset Include Files{#transformation-dataset-include-files}

The Transformation Dataset Include file for an inherited profile contains parameters associated with the transformation phase of dataset construction.

 The first line of the file defines a type [!DNL TransformationInclude] that supports the Extended Dimensions, Parameters, Reprocess, Stage, and Transformations parameters. All other parameters must be defined in the [!DNL Transformation.cfg] file in the dataset profile's Dataset directory.

Including parameters other than Extended Dimensions, Parameters, Reprocess, Stage, and Transformations in a [!DNL Transformation Dataset Include] file generates errors.

You can name a [!DNL Transformation Dataset Include] file anything you want, but its file extension must be [!DNL .cfg]. The file must be stored within the *inherited profile name*\Dataset\Transformation directory. Because the files are loaded recursively during the transformation phase of dataset construction, you can store the [!DNL Transformation Dataset Include] files at any level within the directory (for example, *inherited profile name*\Dataset\Transformation\*folder name*\*include file name*.cfg).

>[!NOTE]
>
>Many web-specific configuration parameters for Site are defined in [!DNL Transformation Dataset Include] files. For information about these parameters, see [Configuration Settings for Web Data](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

The following table describes the parameters that are available in a [!DNL Transformation Dataset Include] file:

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Extended Dimensions </td> 
   <td colname="col2"> Optional. Defines the extended dimensions. See <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-ex-dim.md#concept-79b9e2b3f5794833b8b73b003f06ddca"> Extended Dimensions</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parameters </td> 
   <td colname="col2"> Optional. A variable that you can reference in other configuration parameters. For more information, see <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Defining Parameters in Dataset Include Files</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess </td> 
   <td colname="col2"> <p>Optional. Any character or combination of characters can be entered here. Changing this parameter and saving the file initiates data retransformation. </p> <p> For information about reprocessing your data, see <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823"> Reprocessing and Retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Optional. The name of the processing stage that applies to this <span class="wintitle"> Transformation Dataset Include</span> file. The processing stages are defined in the Stages parameter in the <span class="filepath"> Transformation.cfg</span> file. </p> <p> <p>Note: When you specify a Stage, the name of the Stage must match exactly the name that is listed in the Stages parameter in the <span class="filepath"> Transformation.cfg</span> file for the dataset profile. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Optional. Defines the data transformations that need to be applied during transformation. For information about the available transformation types, see <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-data-trans.md#concept-99c6f5e6e5194adb9e98afdc0e91cf38"> Data Transformations</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>For descriptions of the parameters in the [!DNL Transformation.cfg] file, see [Transformation Configuration File](../../../../home/c-dataset-const-proc/c-trans-config-file/c-trans-config-file.md#concept-cfe9e04d11fd43d980cec36c3c7af211).

You should keep the following points in mind whenever you are working with [!DNL Transformation Dataset Include] files:

* Changing any of the parameters in this file requires retransformation of the data. 
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize], and [!DNL AppendURI] transformations work only when defined in a [!DNL Transformation Dataset Configuration] file. For information about these transformations, see [Data Transformations](../../../../home/c-dataset-const-proc/c-data-trans/c-data-trans.md#concept-99c6f5e6e5194adb9e98afdc0e91cf38). 

* You can add any of the parameters described above to the [!DNL Transformation Dataset Include] file by opening and editing the file in Notepad. Any changes you make and save appear when you reopen the file in data workbench. When adding a new parameter, use the Space key (not the Tab key) to indent two (2) spaces to the right of the previous heading level.

If you subscribe to Adobe's [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] data service, Adobe provides you with an internal profile consisting of a set of data transformations and extended dimensions that are created specifically for the data service. The transformations and dimensions are defined in [!DNL Transformation Dataset Include] files that are included in the Dataset directory of the internal profile. For instructions to install the internal profile for the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] data service, see the *Data Workbench User Guide*. 
