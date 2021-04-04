---
description: To enable controlled experimentation, someone with administrator access to your web or application servers must modify the ExpFile parameter in the Sensor configuration file (usually named using txlogd.conf) on each web or application server in your web cluster on which a Sensor is installed.
solution: Analytics,Analytics
title: Enabling Controlled Experimentation
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
---
# Enabling Controlled Experimentation{#enabling-controlled-experimentation}

To enable controlled experimentation, someone with administrator access to your web or application servers must modify the ExpFile parameter in the Sensor configuration file (usually named using txlogd.conf) on each web or application server in your web cluster on which a Sensor is installed.

In addition, two other parameters in this file can be modified to implement a testing tool (ExpCookieURL parameter) or to remap large sections of your website (ExpPartialMatch parameter). This chapter provides more information about these parameters.

**To edit the txlogd.conf file**

If you have administrator access, complete the following steps. If you do not have administrator access, contact your system architect to request the changes, providing them with the following steps. 

1. Navigate to the [!DNL Sensor] installation folder on a web or application server in your web cluster on which a [!DNL Sensor] is installed.
1. Open the [!DNL Sensor] configuration file (usually named using [!DNL txlogd.conf]) using a text editor and edit the file as indicated in [Modifying the ExpFile Parameter](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   (And optionally in [Modifying the ExpCookieURL Paramter (Optional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) and [Modifying the ExpPartialMatch Parameter (Optional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).) 

1. Save and close the file.
1. Repeat this procedure for each web or application server in your web cluster on which a [!DNL Sensor] is installed.
