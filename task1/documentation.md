# Setting up an Ubuntu Virtual Machine on Azure
This documentaion explains the process of creating and connecting ubuntu virtual machine using Microsoft Azure with  
a student account
## Step 1: Azure Account Setup
1. Create a new azure account
     - Visit [](Portal.azure.com)
     - Sign up using HAMK student ID email
     - Complete the registration process
2. Activate Azure for Students:
     - Add Azure for Students subscription
     - This provides additional credits for your Azure resources
## Step2: Virtual Machine Creation
**Basic Settings**
1. From the Azure Portal dashboard, select "Create a resource"
2. Search for and select "Ubuntu Server 24.04 LTS gen 2" from the Marketplace
3. Configure the following settings:
     - **Resource Group**: Create new and give it a name i.e robotics
     - **Virtual Machine name**: (Any logical name: lab-robotics)
     - **Region**: (North Europe)
     - **Image**:Ubuntu Server 24.04 LTS gen 2
     - **Size**:  Standard_B2ls_v2
 **Authentication**
 - Choose Username and SSH Key
 - Write a username and select **RSA SSH Format** key type
 - write a name in  key pair name
 **Disks**
 - Configure network settings:
 - Select inbound ports and choose **HTTP(80),HTTPS(443),SSH(22)**
 - Select **Standard SSD** for OS disk type
 - Check in the option of **Delete with VM**
**Networking**
 - Select basic for network security group
 - Allow slected ports for public inbound ports
**Managment**
 - Select **Enable auto-shutdown**
 - Choose the time for shutdown
**Monitoring**
 - In the diagnotics section, choose the recommended option

## Connection: 
 - Download the private key to your device
 - To connect with your local machine choose **Native SSH**
 - Copy your path in that section
 - After that open the command prompt and paste that path there and select yes
 - Finally, a connection is made successful




