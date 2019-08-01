---
description: You can open a field viewer as a callout from a dependency map or as a standalone visualization from the Admin menu.
seo-description: You can open a field viewer as a callout from a dependency map or as a standalone visualization from the Admin menu.
seo-title: Create a field viewer
solution: Analytics
title: Create a field viewer
topic: Data workbench
uuid: 5beece5a-6b75-4377-a1f7-5b1b11b91007
index: y
internal: n
snippet: y
---

# Create a field viewer{#create-a-field-viewer}

You can open a field viewer as a callout from a dependency map or as a standalone visualization from the Admin menu.

## Create a field viewer from a dependency map {#section-040cb83c902b49c48b841d35abc127e5}

When you open a field viewer from a dependency map (as shown in [Opening Field Viewers](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), the viewer is populated automatically based on the log source, transformation, or dimension that you right-click. For a log source or a transformation, the fields in the viewer are inputs or outputs of the log source or transformation. For a dimension, the fields are inputs of the dimension. You can add and remove fields as desired.

## Create a field viewers as a standalone visualization {#section-11d10e46631d4fdca45d7534336e1e80}

When you open a field viewer as a standalone visualization, you can create a [!DNL Log Processing Field Viewer] or a [!DNL Transformation Field Viewer]. The viewer is blank, and you must add the desired fields to the viewer. For a [!DNL Log Processing Field Viewer], you can add fields from the [!DNL Log Processing.cfg] file or any [!DNL Log Processing dataset include] file. For a [!DNL Transformation Field Viewer], you can add fields from the [!DNL Transformation.cfg] file or any [!DNL Transformation dataset include] file.

For more information about configuration and include files, see the *Dataset Configuration Guide*.

## Add and remove a field {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**To add a field to a field viewer**

* Right-click within the field viewer and click **[!UICONTROL Fields]** > *< **[!UICONTROL field name]**>* > *< **[!UICONTROL instance]**>*.

  -or- 

* Right-click within an existing column in the field viewer and click **[!UICONTROL Fields]** > *< **[!UICONTROL field name]**>* > *< **[!UICONTROL instance]**>*.

Field name refers to the field’s name, and instance refers to where in the dataset configuration the field is used, such as a dataset processing stage or a transformation. Some fields are used in multiple places within the dataset configuration (for example, a field can be modified by multiple transformations), so you must select which instance of the field to add to your field viewer.

In the list of available fields, an X appears to the left of any field already displayed in the viewer.

**To remove a field from a field viewer**

* Right-click within the column for the field that you want to remove and click **[!UICONTROL Remove Field]**.

