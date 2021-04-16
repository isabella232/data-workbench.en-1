---
description: The ExpFile parameter points to the location of the experiment configuration file, which defines your experiment.
solution: Analytics,Analytics
title: Modifying the ExpFile Parameter
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
---
# Modifying the ExpFile Parameter{#modifying-the-expfile-parameter}

The ExpFile parameter points to the location of the experiment configuration file, which defines your experiment.

Setting this parameter enables you to run experiments. For steps to create the experiment configuration file, see [Configuring and Deploying the Experiment](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Following is an example of the ExpFile parameter: 

```
ExpFile /home/experiment.txt
```

This tab delimited text file ( [!DNL .txt]) can be located anywhere in the [!DNL Sensor] folder and can have any convenient name.

Make sure you record the location of the experiments directory and the name of the configuration file that you specify because you need to save your experiment configuration file (to be described later in this guide) using this name and in this directory.

>[!NOTE]
>
>If you do not set this parameter identically on each machine in your web cluster on which a [!DNL Sensor] is installed, controlled experimentation does not work.

This entry can be preconfigured and remain in the [!DNL Sensor] configuration file on an ongoing basis with no adverse effect. If the experiment configuration file name specified is not found by [!DNL Sensor] or it is blank (that is, it exists but has no content), [!DNL Sensor] does not conduct the experiment, logs an error event on the HTTP server, and continues to operate normally in all other respects.
