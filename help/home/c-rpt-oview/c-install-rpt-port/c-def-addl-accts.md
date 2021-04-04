---
description: Users must have a valid account and provide an account name and password when they access the Report Portal.
solution: Analytics
title: Define Additional Accounts
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
---
# Define Additional Accounts

Users must have a valid account and provide an account name and password when they access the Report Portal.

By default, user authentication is enabled in [!DNL Report Portal].

The list of valid accounts for [!DNL Report Portal] is maintained in the database file, [!DNL portal.mdb]. [!DNL Report Portal] is installed with one account with administrative privileges:

* Account Name: test 
* Password: user

>[!NOTE]
>
>For security reasons, Adobe recommends that you change the password for this account after you install [!DNL Report Portal].

To add user accounts to [!DNL Report Portal] or change information relating to existing accounts, you use the [!DNL Admin] tab on the [!DNL Report Portal] user interface.

Each time you add a new account or edit an existing account, a confirmation email is sent as specified in the [!DNL email.asp] file in the \*PortalName*\PortalASP folder. For more information, see [Edit the Email.asp File](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

For steps to add additional users, see [Working with Accounts](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Optionally, you can disable user authentication and allow anonymous access to [!DNL Report Portal]. For steps to do so, see the information about the Session(“In”) parameter in [Edit the Session Configuration File](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
