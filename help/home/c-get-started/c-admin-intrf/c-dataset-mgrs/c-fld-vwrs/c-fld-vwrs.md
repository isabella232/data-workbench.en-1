---
description: A field viewer is a table containing the values of one or more data fields.
title: Field viewer
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
---
# Field viewer{#field-viewer}

A field viewer is a table containing the values of one or more data fields.

The fields whose values display are inputs or outputs of a dataset’s log sources, transformations, or extended dimensions. The field’s name is shown in the column heading, and each row contains the field’s value for a single row of source data. Because field viewers enable you to see a field’s values, they are helpful in writing and testing [regular expressions](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

You can open a field viewer as a callout from a [!DNL Transformation Dependency] map or as a standalone visualization from the [!DNL Admin] menu:

* Creating a field viewer from a [!DNL Transformation Dependency] map. When you open a field viewer from a [!DNL Transformation Dependency] map, the viewer is populated automatically based on the log source, transformation, or dimension that you right-click. For a log source or a transformation, the fields in the viewer are inputs or outputs of the log source or transformation. For a dimension, the fields are inputs of the dimension. You can add and remove fields as desired. 

* Creating a field viewer as standalone visualization. When you open a field viewer as a standalone visualization, you can create a [!DNL Log Processing Field Viewer] or a [!DNL Transformation Field Viewer]. The viewer is blank, and you must add the desired fields to the viewer. For a [!DNL Log Processing Field Viewer], you can add fields from the [!DNL Log Processing.cfg] file or any [!DNL Log Processing Dataset Include] file. For a [!DNL Transformation Field Viewer], you can add fields from the [!DNL Transformation.cfg] file or any [!DNL Transformation Dataset Include] file.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Field viewers are not table visualizations; therefore, they do not have the properties associated with tables.

For information about adding and removing fields and filtering within a field viewer, see [Administrative Interfaces](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
