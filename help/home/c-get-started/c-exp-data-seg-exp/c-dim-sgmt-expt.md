---
description: Any data that you want to export must be defined as a dimension within the profile.
title: Create dimensions for use with segment export
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
---
# Create dimensions for use with segment export{#create-dimensions-for-use-with-segment-export}

Any data that you want to export must be defined as a dimension within the profile.

 If the dimension does not already exist in the profile, you must create it. You can create dimensions using any of the following methods:

* Add a dimension to the [!DNL Transformation.cfg] file. See the *Dataset Configuration Guide*. 

* Create a new [!DNL .dim] file. See [Creating and Editing Derived Dimensions](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93). 

* Make selections in a visualization such as a process map or a segment and save the selections as a dimension. See [Saving Dimensions from Process Maps](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) and [Creating Segment Dimensions](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

Exporting a field of data such as Tracking ID or Email Address (which can have lots of elements) requires that you create a denormal dimension that stores the raw strings of data.

For more information about denormal dimensions, see the *Dataset Configuration Guide*.
