---
description: Steps to deploy the dashboard in IIS.
solution: Analytics
title: Deploying the Dashboard
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
---

# Deploying the Dashboard{#deploying-the-dashboard}

Steps to deploy the dashboard in IIS.

1. Create an installation folder to install the dashboard, such as [!DNL c:\inetpub\wwwroot\dashboard].
1. Create the dashboard’s application pool in IIS.
1. Open the IIS Manager Console.
1. Go to **[!UICONTROL Application Pools]**.
1. Select **[!UICONTROL Add Application Pool…]**in the **[!UICONTROL Actions]** menu to the right.
1. In the **[!UICONTROL Add Application Pool]** form, use the dashboard for the name and select .NET Framework v.4.0.xxxxxx as your .NET Framework Version.
1. Leave other fields as their default and click **[!UICONTROL OK]** to create the application pool.
1. Deploy the dashboard application.
1. Open the IIS Manager Console.
1. Expand the **[!UICONTROL Default Web Site]**, you should see the folder you created in c:\inetpub\wwwroot\dashboard by default.
1. Right-click the folder and select **[!UICONTROL Convert to Application]**.
1. Select the **[!UICONTROL Application Pool]**created in Step 2 (for example, “Dashboard”).
1. Under **[!UICONTROL Sites]**, right-click the web site to which you wish to deploy (for example, “Default Web Site”).
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Browse to and select the dashboard deployment file provided by Adobe.
1. Click **[!UICONTROL Next]** twice to proceed to the Enter Application Information screen.
1. From this screen, you can choose to customize your dashboard deployment.
1. For **[!UICONTROL Application Path]**, enter the folder name previously selected.
1. Under **[!UICONTROL Disable Automatic Database Upgrade]**, enter `False`, since this is a new installation.
1. Customize your connection string, if necessary. For example:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Click **[!UICONTROL Next]** and IIS will begin installing the application.
1. Once the installation has completed, you should see no errors in the installation log.
