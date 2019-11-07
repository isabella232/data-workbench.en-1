---
description: Instructions to install and configure an Insight Server FSU for use with Repeater.
solution: Insight
title: Configuring an Insight Server FSU for Repeater
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
---

# Configuring an Insight Server FSU for Repeater{#configuring-an-insight-server-fsu-for-repeater}

Instructions to install and configure an Insight Server FSU for use with Repeater.

Complete the following tasks in order. Any exceptions or changes that you must make so that the [!DNL Insight Server] FSU can be used as a repeater server are noted after each step. 

1. Install the [!DNL Insight Server] program files as described in [Installing Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Because the machine on which you install these files is used to run Repeater, it is helpful to give the installation directory a descriptive name such as [!DNL D:\Adobe\Repeater]. 

1. Install the [!DNL Insight Server] digital certificate as described in [Downloading and Installing the Digital Certificates](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   After you have logged in to the Adobe License Server, remember to look for the certificate name that matches the server common name of the designated repeater machine. 

1. Check the port settings in the [!DNL Communications.cfg] file as described in [Checking the Port Settings](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   If the assigned ports (Port and SSL Port) are used by another process running on the same machine, you must change the port assignments to an unused pair. 

1. If necessary, change the log directory for the [!DNL Sensor] data to be collected and stored on this machine. For instructions, see [Monitoring Event Data Space](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Modify the [!DNL Access Control.cfg] file to allow administrative access to [!DNL Insight Server] from [!DNL Insight] as described in [Updating the Access Control File](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modify the [!DNL server.address] file to define the server’s network location as defined in [Defining the Server's Network Location](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Set Windows memory utilization parameters.
1. Register [!DNL Insight Server] as a Windows service as described in [Registering Insight Server as a Windows Service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
