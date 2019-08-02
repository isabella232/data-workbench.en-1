---
description: Encrypt passwords and other strings when communicating between the client and server.
seo-description: Encrypt passwords and other strings when communicating between the client and server.
seo-title: String Encryption
title: String Encryption
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
index: y
internal: n
snippet: y
---

# String Encryption{#string-encryption}

Encrypt passwords and other strings when communicating between the client and server.

When communicating between the Data Workbench client (workstation) and server, you can save a Value parameter (such as a password) with the Type of *EncryptedString*. This hides the parameter and saves the string to the *Windows Credential Store* on the server with the corresponding key returned. This primarily stores credentials used in exports but can be used to encrypt any parameter.

* A new folder was added at Server\**EncryptStrings**.

  This is where you set the configuration file to encrypt strings. 

* A new configuration file was added at Server\Component\**EncryptedStrings.cfg**.

  ```
  component = EncryptionComponent:
    Path = Path: EncryptStrings\\*.cfg
  ```

  This file polls the *Server*\*EncryptStrings* folder for encryption configuration files.

****

**To encrypt a string**:

1. Create an **EncryptedStrings.cfg** configuration file for a string with these fields set:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

    * *Value* - This field contains the plain text string that needs to encrypted.

      This is server-side encryption only. The *Value* setting is encrypted only on the server computer. 
    
    * *Name* - This field contains a value identifying the encrypted string. 
    * *EncryptValue* - This field will be left empty in the input configuration file. The encrypted value will be returned in this field.

   You can add multiple **NameEncryptValuePair** values for different fields for encryption.

   >[!NOTE]
   >
   >All empty Value fields will be removed. 
   >
   >

1. Save the **EncryptedStrings.cfg** file to the Server\**EncryptStrings** folder.

**Output file**

An output file will be generated with the same name as the input file with a <*filename*>.*encrypted* extension. For example, if the input file is named *sample.cfg* then the output file will be named *sample.cfg.encrypted*. 
