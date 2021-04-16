---
description: Data Workbench can be configured to allow only certain users to change certain workspaces.
title: Configure a locked workspace
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
---
# Configure a locked workspace{#configure-a-locked-workspace}

Data Workbench can be configured to allow only certain users to change certain workspaces.

 While a workspace is locked, users can make selections in most visualizations and sort the data in tables but cannot otherwise change the workspace. This functionality prevents users from making unintentional changes to the workspaces.

The following three elements work together to control the locking of workspaces:

* **A folder.lock or *workspace name*.lock file:** A [!DNL folder.lock] file specifies whether the workspaces in a particular folder are locked, while a workspace [!DNL name.lock] file specifies whether a particular workspace is locked. 

* **The Unlock parameter in a user’s [!DNL Insight.cfg] file:** This parameter specifies whether that user can temporarily unlock locked workspaces. 
* **The Temporarily Unlock menu option:** When the Unlock parameter in the user’s [!DNL Insight.cfg] is set to true, this option appears automatically in the title bar menu of each locked workspace to provide a way for the user to unlock it.

For information about [!DNL folder.lock] and workspace [!DNL name.lock] files, see the following section. For information about setting the Unlock parameter, see [Setting the Unlock Parameter](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). For information about the [!DNL Temporarily Unlock menu] option, see [Unlocking a Workspace](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
