---
description: The administrative tasks for repeater functionality are very similar to those for Insight Server.
seo-description: The administrative tasks for repeater functionality are very similar to those for Insight Server.
seo-title: Administering Repeater
solution: Insight
title: Administering Repeater
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
index: y
internal: n
snippet: y
---

# Administering Repeater{#administering-repeater}

The administrative tasks for repeater functionality are very similar to those for Insight Server.

The following administrative tasks apply; exceptions or changes that you must make so that the [!DNL Insight Server] DPU can be used with the repeater server are noted after each step.

* [Re-validating the Digital Certificate](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c) 
* [Confirming that the Service Is Running](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) In the list of services in the Services control panel, look for “Repeater.” 

* [Configuring Access Control](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d) 
* [Monitoring Disk Space](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) The data types that apply to the repeater server are event, operating system, and system data. If you are using the repeater server for backup storage and it becomes necessary to make more data storage space available on the machine, you can move all but the most current day’s log files to another machine or data storage medium (zip drive, tape, and so forth). Moving the data does not require you to stop the repeater service.

  >[!NOTE]
  >
  >You should verify the integrity of the backup copies of your [!DNL .vsl] files before deleting any of them from Repeater.

* [Configuring Administrative Alerts](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa) 
* [Monitoring Administrative Events](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34) 
* [Monitoring Audit Logs](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231) 
* [Configuring Communications](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec) 
* [Restarting the Service](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] functionality is designed to run continuously. If you restart the machine, repeater restarts automatically. If you need to start and stop repeater manually, you can do so using the Services control panel in Windows.

