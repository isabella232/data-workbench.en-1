---
description: Typically, you want to add an Insight Server DPU to an existing cluster when the amount of data you want to process and make accessible to your users of Insight and Report exceeds the capacity of your cluster’s current configuration.
title: Adding an Insight Server DPU to an Existing Cluster
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
---
# Adding an Insight Server DPU to an Existing Cluster{#adding-an-insight-server-dpu-to-an-existing-cluster}

Typically, you want to add an Insight Server DPU to an existing cluster when the amount of data you want to process and make accessible to your users of Insight and Report exceeds the capacity of your cluster’s current configuration.

## Updating the Configuration Files on the Master Server {#section-7c9a23754a994d73b722d53f999f0e82}

In [!DNL Insight], open up the [!DNL Server Files Manager] for your master [!DNL Insight Server] (usually an [!DNL Insight Server] FSU) and do the following for each DPU that you want to add to the cluster:

1. Edit the address file on the master [!DNL Insight Server] to include the name and address of the new DPU as described in [Adding the Processing Insight Servers to the Address File](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Add the name and address of the new DPU to the group in which your cluster’s current [!DNL Insight Servers] are listed. 

1. Edit the access control file on the master [!DNL Insight Server] to include the IP address of the new DPU as described in [Updating the Access Control File for a Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installing the New Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

This task applies only to Windows 32 bit.

1. Copy the following directories from one of the current DPUs in your cluster to the new DPU:

    * [!DNL Insight Server] installation directory/bin/ 
    * [!DNL Insight Server] installation directory/Certificates/ 
    * [!DNL Insight Server] installation directory/Components/

1. Download and install the digital certificate for the new DPU as described in [Downloading and Installing the Digital Certificates](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17). 
1. Set the Windows memory utilization parameters on the new DPU. 
1. Register [!DNL Insight Server] as a Windows service on the new DPU machine as described in [Registering Insight Server as a Windows Service](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540). 

1. Check the Trace logs to make sure that the DPU is synchronizing to the master [!DNL Insight Server]. 
1. Repeat steps 1 through 6 for each additional DPU that you are adding to the cluster.

## Adding the New Insight Server DPU to the Dataset Profile’s Processing Servers {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

If the new DPU processes the same dataset as the other DPUs in the cluster, add the common name of the new DPU to the [!DNL profile.cfg] file on master [!DNL Insight Server] as described in [Specifying the Processing Servers in Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
