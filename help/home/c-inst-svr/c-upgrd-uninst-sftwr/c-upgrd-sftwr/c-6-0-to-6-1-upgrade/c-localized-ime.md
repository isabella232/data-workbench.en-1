---
description: Data workbench now supports the Input Method Editor (IME) as a secondary text entry process for international languages.
solution: Analytics
title: Installing the Input Method Editor
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
exl-id: 0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec
exl-id: e4e1c016-0544-434a-b82e-fdd2a4af316c
---
# Installing the Input Method Editor{#installing-the-input-method-editor}

Data workbench now supports the Input Method Editor (IME) as a secondary text entry process for international languages.

IMEs allow you to enter international characters using a variety of methods suited for your local language. Data workbench provides an input dialog box that allows you to open and use your desired IME for text fields.

>[!NOTE]
>
>For the data workbench 6.1 release, only the virtual Simplified Chinese keyboard will be supported. Inputting other languages through the IME could result in unexpected behavior.

## Using an IME {#section-5f008d75a7b24119ab6aebc55454f927}

To use the floating IME text input feature:

1. Click **[!UICONTROL Alt + Space]** for any text input area. 
1. Enter values using your system's IME. 
1. Close the input dialog by selecting the **[!UICONTROL Enter]** key or clicking the **[!UICONTROL OK]** button.

   The dialog will disappear and the characters will then appear in the selected field.

**Updating the Insight.cfg file**

To employ the IME, you must update the [!DNL Insight.cfg] file with this setting:

```
Localized IME = bool: true
```

If this setting does not exist in the configuration file, then pressing **[!UICONTROL Alt + Space]** will not engage the IME feature.

**Starting Insight in another language:** To better support localized assets like a splash screen and to support multiple languages in the future, data workbench requires command-line arguments identifying the language to load. The default language is English.

Starting data workbench in Chinese requires you to invoke [!DNL Insight.exe] with the "-zh-cn" argument:

```
Insight.exe -zh-cn
```

(These command line arguments are not case sensitive.)
