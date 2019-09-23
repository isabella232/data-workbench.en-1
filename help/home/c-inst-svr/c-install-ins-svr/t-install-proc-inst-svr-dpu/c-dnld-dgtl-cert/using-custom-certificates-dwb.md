---
description: Instructions for using custom certificates.
seo-description: Instructions for using custom certificates.
seo-title: Using Custom Certificates in Data Workbench
title: Using Custom Certificates in Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
---

# Using Custom Certificates in Data Workbench{#using-custom-certificates-in-data-workbench}

Instructions for using custom certificates.

A certificate used by either the Data Workbench client or server needs to be signed by a trusted CA (Certificate Authority). Data Workbench customers receive certificates that are signed by the Visual Sciences CA. These certificates are trusted by the Data Workbench software, since the [!DNL trust_ca_cert.pem] (provided along with the Insight software and stored in the **Certificates** directory of both servers and clients) contains a *Root CA Certificate* for the Visual Sciences CA. These certificates are used for both licensing of the software and authentication when clients and servers communicate with each other using SSL. Only certificates issued by the Visual Sciences CA can be used for licensing, but other certificates may be used for communication and authentication. Certificates issued by CAs other than Visual Sciences are referred to below as *custom certificates.*

**Important note:** For servers and clients, Data Workbench software uses the certificate files installed in the client or server's **Certificates** directory or certificates explicitly identified in its configuration. However, you can also use the [Windows Certificate Store](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) for clients.

The following instructions describe the procedures to be followed to use custom certificates for communication between Data Workbench clients and servers. Not every detail is a hard requirement and different variations in the process can be employed. However, the procedures below have been tested to work.

## Setting up Custom Client Certificates {#section-2083fd41973e451fa404e7a4ae4da591}

1. Add the certificate of the issuing CA to the [!DNL trust_cert_ca.pem], which is installed in the **Certificates** directory of the client and that of every server in every cluster that is to be accessed using this custom certificate. 

1. Obtain a custom certificate for each server in the cluster with the following conditions:

    1. Certificate is formatted as a [!DNL .pem] certificate. 
    1. Certificate contains its key and is unencrypted (i.e., it has no password/pass phrase).

       A certificate contains its key with one of the following lines:     
    
       ```    
       BEGIN PRIVATE KEY 
       BEGIN RSA PRIVATE KEY
       ```

       One way to remove the password phrase from a [!DNL .pem] certificate:

       ```    
       openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
       openssl x509 -in password-protected-cert.pem >> no-password.pem
       ```

    1. Certificate has the CN, O, OU, etc. as required for this client in the servers' [!DNL Access Control.cfg] file. 
    1. Certificate was issued with a *purpose &#42;&#42;&#42;* of *client* (or both *server* **and** *client*).

       To verify that a certificate has a purpose code of server and/or client, the following commands can be used:     
    
       ```    
       openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
       openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
       ```    
    
       For a server certificates, both commands should yield:     
    
       ```    
       custom_communications_cert.pem: OK
       ```    
    
       For a client certificate, only the second command is required to yield [!DNL OK].

1. Place the certificate in the client's **Certificates** directory. 
1. In [!DNL Insight.cfg] under the *serverInfo* for each cluster that you want to use this certificate, make sure the *custom client cert* is named, such as:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:  
<b>my_custom_client_cert.pem</b>
   ```

## Setting up Custom Server Certificates {#setting-up-custom-server-certificates}

This section assumes that you have a cluster that is up and running, using Visual Sciences issued certificates, and the configuration follows common practices (such as the *Components for Processing Servers* directory on the master gets synchronized to the *Components* directories of all DPUs).

1. Add the certificate of the issuing CA to the [!DNL trust_cert_ca.pem] which is installed on every server in the cluster and every client that needs to communicate with this cluster. 
1. Obtain a custom certificate for each server in the cluster with these requirements:

    1. Custom certificate is formatted as a [!DNL .pem] certificate. 
    1. Certificate contains its key and is unencrypted (i.e., it has no password/pass phrase).

       A certificate contains its key if it has a line such as:

       ```    
       BEGIN PRIVATE KEY 
       BEGIN RSA PRIVATE KEY
       ```    
    
       One way to remove the password phrase from a [!DNL .pem] certificate:

       ```    
       openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
       openssl x509 -in password-protected-cert.pem >> no-password.pem
       ```

    1. Certificate has the same CN as the [!DNL server_cert.pem] currently installed on the server. 
    1. Certificate was issued with a purpose of *server* and *client*.

       To verify that a certificate has a purpose code of server and/or client, the following commands can be used:     
    
       ```    
       openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
       openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
       ```    
    
       For a server certificates, both commands should yield:     
    
       ```    
       custom_communications_cert.pem: OK
       ```    
    
       For a client certificate, only the second command is required to yield [!DNL OK].

1. Install each server's custom certificate in the **Certificates** directory of the server as [!DNL custom_communications_cert.pem]. 

1. Using a text editor, add the following line to **Communications.cfg** file in both the *Components* and *Components for Processing Servers* directories, directly below the first line ( [!DNL component = CommServer]): 

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Restart all servers.

**About Certificate Failure Warning**

When the Insight server or client is looking for a **license** certificate in the **Certificates** directory, it tries to validate all the certificates (except [!DNL trust_ca_cert.pem]), against a hard coded copy of the Insight CA certificate, which fails on any custom certificate present in the directory. The server issues this warning:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

This warning can be safely ignored. 
