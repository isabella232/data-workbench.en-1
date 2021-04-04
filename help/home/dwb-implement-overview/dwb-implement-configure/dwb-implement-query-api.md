---
description: A quick guide for setting up a Query API.
title: Query API Setup
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
---
# Query API Setup{#query-api-setup}

A quick guide for setting up a Query API.

Follow the below steps for setting up the Query API:

1. Query API Certificate Acquisition

   Send an Email to the Tech Ops Team of Adobe Email - `Dataworkbench@adobe.com`.

   Please provide the CN name you want to use for the Query API( provide a generic name like `<Client>` Query API). 

   >[!NOTE]
   >
   >Tech Ops will generate the certificate and upload it in a URL. Please let the Adobe Consultants know after receiving the notification from Tech Ops on successful generation of the ticket so that the ticket will be sent to you by them back.

1. Downloading and Extracting the API Stunnel. Receive the api-stunnel file from you consultant.

   Make sure Perl is installed on your machine.

   In the extracted folder (the folder path where you copy the file), copy your Query API certificate inside the *stunnel* folder. 

1. Configure the Stunnel.conf

   There should be a file called *stunnel.conf* inside the *Stunnel* folder (where you copied your certificate).

   Edit the file in Notepad. 

   ![](assets/dwb_impl_API1.png)

   Change the parameters as follows: ![](assets/dwb_impl_API2.png)

   Two parameters need to be changed in this file.

    * *Cert* = The name on your certificate. In this example it is Aadhithiya Ramani QAPI Client.pem. 
    * *Connect* =The server name for your main DPU.

1. Copying the *Query.pm*.

   The *Query.pm* file will be available in the Insight API Folder.

   Copy the *Query.pm* file and paste it in your Perl Library folder(usually it will be *C:\Perl64\lib *, but check where the Perl is installed in your machine). 

1. Modify the *api-http.pl* file

   The api-http.pl file will be available in the api-stunnel folder.

   Only one parameter to be modified

   *My $profile* = The profile name for which you are configuring the Query API. 

1. Instal the Query API.

   Open the command prompt in your system as "Administrator" and navigate to the directory where you extracted the *stunnel* as shown: ![](assets/dwb_impl_API3.png)

   Run the following command *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   After executing the command a window will pop stating that the *stunnel* is installed.

   >[!NOTE]
   >
   >After executing the command a window will pop stating that the *stunnel* is installed.

1. Testing the Query API stunnel configuration

   The Final step of this process will be to test the Query API configuration. In the command prompt which you used for installing the api-stunnel directory. ![](assets/dwb_impl_API5.png)

   Run the Perl script available in that folder using the following command* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   After running the script the results should be like the screenshot below (the date time and values in the result will vary according to the as of time and other paramters in the profile on which you have configured the Query API (in step 6). ![](assets/dwb_impl_API7.png)
