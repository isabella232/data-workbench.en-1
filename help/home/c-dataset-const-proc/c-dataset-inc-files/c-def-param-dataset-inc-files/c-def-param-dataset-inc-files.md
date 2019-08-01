---
description: When configuring your dataset, you can define variables, referred as parameters, to represent meaningful values.
seo-description: When configuring your dataset, you can define variables, referred as parameters, to represent meaningful values.
seo-title: Defining Parameters in Dataset Include Files
solution: Analytics
title: Defining Parameters in Dataset Include Files
topic: Data workbench
uuid: 9cfae38b-d070-46f2-b444-43749f8bfe07
index: y
internal: n
snippet: y
---

# Defining Parameters in Dataset Include Files{#defining-parameters-in-dataset-include-files}

When configuring your dataset, you can define variables, referred as parameters, to represent meaningful values.

 To assign a value to a parameter (that is, to define the parameter), you add the parameter's name and value to the Parameters vector in a log processing or [!DNL Transformation Dataset Include] file. After you define parameters, you can reference them in your dataset profile's configuration files. Defining and referencing such parameters is referred to as parameter substitution. Using parameter substitution when configuring your dataset enables you to create a centralized location for your parameter definitions. When you need to update a parameter that is referenced multiple times or in multiple files, you have to make the change only once.

>[!NOTE]
>
>In this guide, the term parameter has been used to refer to the name of any setting in a configuration file (such as Log Entry Condition, Reprocess, or Transformations). However, as used in this section, parameter refers specifically to a member of the Parameters vector in a dataset include file and not to the name of a setting in a configuration file.

You should consider the following points when defining a parameter:

* A parameter must be defined exactly once. Therefore, you cannot define the same variable in multiple dataset include files. 
* Any parameter that you define is local to either the log processing or the transformation phases, but it is global across multiple dataset configuration files for that phase. For example, if you define a parameter in a [!DNL Transformation Dataset Include] file, the parameter is defined for the entire transformation phase, and you can reference it in the [!DNL Transformation.cfg] file and all other [!DNL Transformation Dataset Include] files for the inherited profiles. The parameter would not be defined for log processing; therefore, any references to the parameter in the [!DNL Log Processing.cfg] file or a [!DNL Log Processing Dataset Include] file would generate a processing error.

**To define a parameter**

You can define string, numeric, and vector parameters in [!DNL Log Processing] and [!DNL Transformation Include] files.

1. In the data workbench window for the [!DNL Log Processing] or [!DNL Transformation Dataset Include] file, right-click **[!UICONTROL Parameters]**, then click **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**. 

1. Select **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]**, or **[!UICONTROL Vector Parameter]**, and complete the Name and Value parameters as described in the following sections. 

1. To save the dataset include file in which you have defined the parameter, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

>[!NOTE]
>
>Do not save the modified configuration file to any of the internal profiles provided by Adobe, as your changes are overwritten when you install updates to these profiles.

**To reference a parameter**

* When you reference a defined parameter in another dataset configuration file, you must type its name as [!DNL $(parameter name)].

The following sections describe the types of parameters that you can define.

* [String and Numeric Parameters](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080) 
* [Vector Parameters](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

