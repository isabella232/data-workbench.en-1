---
description: When you display dataset components on a dependency map, you have the option to enable the Include File Blocks display option.
title: File blocks
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
---
# File blocks{#file-blocks}

When you display dataset components on a dependency map, you have the option to enable the Include File Blocks display option.

 When this option is enabled, the map displays a single blue node for all of the transformations defined in one dataset configuration file and a single green node for all of the extended dimensions defined in one dataset configuration file. For example, if a [!DNL log processing dataset include] file includes the definitions of three transformations, the map displays one blue node representing the three transformations. Similarly, if a [!DNL transformation dataset include] file includes the definitions of two extended dimensions, the map displays one green node representing the two extended dimensions.

## Transformation blocks {#section-c442730394264a0b850792a32eaaa2da}

Each blue node is a transformation block and has the following options:

* To view the input fields of the transformation block, right-click the node for the block and click **[!UICONTROL Inputs]**. 
* To view the output fields of the transformation block, right-click the node for the block and click **[!UICONTROL Outputs]**. 
* To edit any of the transformations in the block, right-click the node for the block and click **[!UICONTROL Edit Configuration]**. The callout that displays contains the entire configuration file in which all of the transformations are defined. You then can edit the parameters as desired. For more information about these parameters, see the *Dataset Configuration Guide*. 

* To see all of the transformations in the block, right-click the node for the transformation block and click **[!UICONTROL Show Details]**. The callout that displays contains another dependency map showing nodes for all of the transformations in the block.

## Dimension blocks {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Each green node is a dimension block and has the following options:

* To view the input fields or the parent dimension of the dimension block, right-click the node for the block and click **[!UICONTROL Inputs]**. 
* To view the output dimensions of the dimension block, right-click the node for the block and click **[!UICONTROL Outputs]**.
