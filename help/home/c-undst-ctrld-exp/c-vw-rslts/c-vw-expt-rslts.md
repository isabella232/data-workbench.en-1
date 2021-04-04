---
description: After you have added the new field to Log Processing.cfg and created the new Split transformation and extended dimension, you can view the new extended dimension that you created as soon as the Fast Input stage of data reprocessing has finished.
solution: Analytics,Analytics
title: Viewing the Experiment Results
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
---
# Viewing the Experiment Results{#viewing-the-experiment-results}

After you have added the new field to Log Processing.cfg and created the new Split transformation and extended dimension, you can view the new extended dimension that you created as soon as the Fast Input stage of data reprocessing has finished.

 This dimension, by default, displays the number of sessions for each of your experiment groups.

**To view the experiment dimension**

* Within any workspace in [!DNL Insight], open a table with the experiment dimension that you created.

  The experiment dimension elements, which represent each experiment you are currently running and each group within each experiment, display with the current number of sessions for each group. Each group is named in the following format using the experiment name followed by the group name:

  *Experiment Name.Group Name*

  For example: [!DNL New Homepage.Control]

The following table shows the Controlled Experiment Groups dimension that was created in [!DNL Transformation.cfg] and each of the experiments and their groups.

The New Homepage experiment is shown at the bottom of the table with its two groups: Control and index2.

![](assets/controlledexpgrps.png)

You now can use the experiment dimension and any relevant metrics to explore and interpret the experiment results, as well as create useful reports detailing those results.
