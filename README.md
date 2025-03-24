## How to Install Splunk Universal Forwarder on Windows

www.splunk.com is a member of the site and the Splunk Universal Forwarder application is downloaded and installed.
### Splunk Universal Forwarder Installation steps;
We run the downloaded Setup file.

![image](https://github.com/user-attachments/assets/0a7afcbb-5740-406e-90f5-5c76b560cc42) © Splunk Inc.

On the first screen that comes up when the installation starts,  we must click on the box at the top and accept the license agreement. Otherwise, we will not be able to continue the installation process. When you click the box, the "Customize Options" and "Next" buttons at the bottom will be active. If we want to change and customize some installation settings, we press the "Customize Options" button. If we want to install it without making any setting changes, we press the "Next" button and proceed. After pressing the Next button, we go directly to the loading screen. Now, let's click the "Customize Options" button and see the settings there.

![image](https://github.com/user-attachments/assets/4f086da4-c6a7-45a7-82e9-b07ebaa3c89a) © Splunk Inc.

Here, it asks in which location we want to install the program. By default, it specifies that it will be installed in C:\Program Files\SplunkUniversalForwarder\. If we want to change it, we can change the location by pressing the "Change" button. Afterwards, we proceed by pressing the "Next" button.

![image](https://github.com/user-attachments/assets/60863c81-c7eb-454c-ae6f-0fd7bc5ce020) © Splunk Inc.

Here, if we have a certificate of our own that we want to identify, we define it. When installing Splunk Universal Forwarder, the certificate identification section is used to ensure that data is transmitted securely encrypted. These certificates typically help secure data transmission between the Splunk forwarder and the Splunk indexer. The purpose of the certificates is to ensure the protection of data using the TLS (Transport Layer Security) encryption protocol. This is especially crucial in situations where sensitive data needs to be transmitted. The transmitted data is encrypted, the integrity of the data is maintained, and the identities of both parties in communication are verified. This security measure is especially important when transmitting data on open networks. If you are working in a small environment, you can use self-signed certificates, but for larger, corporate and secure environments, a CA-signed certificate is more appropriate. We proceed by pressing the "Next" button.

![image](https://github.com/user-attachments/assets/58675633-74d1-4551-a1ba-31c076470062) © Splunk Inc.

- If you are building an installation that will only work on the local system and does not require network access, "Local System" may be sufficient.

- If you are going to work on the network and need access to domain resources, it would be more appropriate to choose "Domain Account".

- "Virtual Account", on the other hand, is used according to security and isolated transaction requirements.

- Here, we select the "Local System" option and say "Next" and proceed.

![image](https://github.com/user-attachments/assets/59a9e198-96c5-4221-aded-e1d7368e9f66) © Splunk Inc.

Here, we click on the relevant boxes to determine which Logs we want  Splunk Universal Forwarder to send to Splunk Enterprise from the device on which it is installed, and then click the "Next" button to proceed.

![image](https://github.com/user-attachments/assets/776d07c0-2181-407d-94ab-0c02eec704b9) © Splunk Inc.

Here, it asks us  to set a username and password for ourselves. We should write down this information as we may be asked to make any adjustments to Splunk Universal Forwarder in the future. We proceed by pressing the "Next" button.

![image](https://github.com/user-attachments/assets/cc0f6434-7673-4fb0-a5b2-0baf2d27327e) © Splunk Inc.

### What is Deployment Server?
Deployment Server provides centralized configuration and application deployment to Universal Forwarders (and other Splunk components) in the Splunk environment. This means that Deployment Server works as a "central configuration server", which allows you to manage each forwarder in batches without having to configure it manually. The Deployment Server stores certain configuration files (for example, inputs.conf, outputs.conf, props.conf, etc.). Automatically forwards to Splunk Universal Forwarders. Different configurations can be distributed to forwarders. For example, different log collection and forwarding settings can be made for different groups of forwarders. When any changes are made, this change is automatically applied to all destination forwarders.
### When to Choose the "Deployment Server" Option
If you plan to centrally manage many Universal Forwarders and want to automatically distribute configuration files to each forwarder, enabling Deployment Server may be a good option. If you are only installing a single Splunk Forwarder and do not need centralized management, you do not need to choose the Deployment Server option. Deployment Server is used to centrally manage multiple Forwarders in a Splunk environment and deploy their configurations. We proceed by pressing the "Next" button.

![image](https://github.com/user-attachments/assets/dfeb0f8f-ca77-49e5-8f03-3d82457d2562) © Splunk Inc.

This option determines where the Universal Forwarder sends the log data it collects. The terms "Receiver" and "Indexer" refer to the components of Splunk through which data is processed and stored.
### What are Receiver and Indexer?

### Receiver
The Splunk Receiver is the point where the data is received. This is usually Indexer in Splunk Enterprise or Splunk Cloud. The receiver receives the data streams and sends this data for later indexing (processing). That is, Forwarders send data to the Receiver.

### Indexer
Indexer is the component where Splunk processes and indexes data. This is the component where the data becomes searchable and the Splunk search engine works. Indexer takes the data, processes it, and then stores the data in a searchable format.

### When to Use the Receiver Indexer Option
Receiver Indexer specifies the Splunk instance from which your Forwarder will receive the data. That is, the Forwarder is configured to send data to a Receiver or Indexer.
When you select this option, Forwarder: It will forward the data it collects to a specific Receiver or Indexer. If you have a central Splunk Enterprise Indexer, data will be sent to this Indexer.

### Summarize
The Receiver Indexer is used to determine where the Universal Forwarder will send the data. This allows data to be transmitted to a central Splunk Indexer. This indexer then indexes the data and makes it searchable. If the data needs to be sent to an Indexer in Splunk Enterprise or Splunk Cloud, you will need to select this option. Here we write the IP number and port 9997 of our Splunk Enterprise. Logs will be sent to this port. That's why Splunk Enterprise's port 9997 must be open. I will explain how to open this port later. . We proceed by pressing the "Next" button.

![image](https://github.com/user-attachments/assets/d66d15f1-1f75-41c0-8b08-cc0a7554715f) © Splunk Inc.

Now we press the "Install" button and start the installation. 

![image](https://github.com/user-attachments/assets/05f8ad44-d2d1-448e-b18f-db82ea6c0ff0) © Splunk Inc.

When  the installation is finished, a screen with a "Finish" button will appear. When you click the Finish button, our Splunk Universal Forwarder installation is completed.

![image](https://github.com/user-attachments/assets/7ddc6de7-3ed8-4e76-b637-fe663b2492b5)

In order for Splunk Universal Forwarder to work, we must right-click on Splunk Forwarder in the Services section in the Task Manager and do Restart.

### Note
This content has been prepared for personal learning purposes related to the installation of Splunk software. All screenshots and software are the property of Splunk Inc. This page is not intended for commercial use.
