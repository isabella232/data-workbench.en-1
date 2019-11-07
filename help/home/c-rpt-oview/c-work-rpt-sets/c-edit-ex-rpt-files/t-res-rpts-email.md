---
description: Steps to resend reports by email.
solution: Analytics
title: Resending Reports by Email
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
---

# Resending Reports by Email{#resending-reports-by-email}

Steps to resend reports by email.

If the **[!UICONTROL Allow Report Regeneration]** parameter in the [!DNL Report.cfg] file is set to [!DNL True], when you make changes to a [!DNL Report.cfg] file and save that file back to the server, Report Server automatically re-generates the reports in that set. It does not resend the reports via email. 

1. On the [!DNL Reports] tab, select the subfolder (tab or drop-down subdirectory) for the report set that you want to resend.
1. Click **[!UICONTROL Report.cfg]**. The parameters of the [!DNL Report.cfg] for this report set display.
1. Change the **[!UICONTROL Start Date]** parameter to the future time at which you want to reports to be resent.
1. Save the file by right-clicking **[!UICONTROL Report.cfg (modified)]** at the top of the parameters and clicking **[!UICONTROL Save to]***< **[!UICONTROL server location]**>*.
The reports in this set regenerate and are resent by email to the specified recipients. 
