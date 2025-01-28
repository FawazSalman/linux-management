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
## Step 2: Virtual Machine Creation
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
Here is the screenshot of all the settings that we made so far:
![Pic of basic settings](https://github.com/FawazSalman/linux-management/blob/main/task1/images/azure2.png?raw=true)
## Connection: 
 - Download the private key to your device
 - To connect with your local machine choose **Native SSH**
 - Copy your path in that section
 - After that open the command prompt and paste that path there and select yes
 - Finally, a connection is made successful
![](https://github.com/FawazSalman/linux-management/blob/main/task1/images/azure3.png?raw=true)
---
# Linux User and File Management Tasks

## Overview
This repository documents the process of managing users and setting up file access permissions in a Linux environment using a **Microsoft Virtual Machine**. The tasks involve creating users, modifying permissions, and ensuring secure access control.

## Task 1: Create the `Tupu` User
![](https://github.com/FawazSalman/linux-management/blob/main/task1/images/task_one.png)
I created the `tupu` user using the `adduser` command:
```bash
sudo adduser tupu
```
This command automatically creates the user, home directory, and sets up the necessary configurations.

---

## Task 2: Create the `Lupu` User
![](https://github.com/FawazSalman/linux-management/blob/main/task1/images/task_two.png)
To create the `lupu` user with a similar setup as `tupu`, I used the `useradd` command:
```bash
sudo useradd -m -d /home/lupu -s /bin/bash -G lupu lupu
```
- `-m`: Creates the home directory
- `-d /home/lupu`: Specifies the home directory path
- `-s /bin/bash`: Sets the login shell to `/bin/bash`
- `-G lupu`: Adds the user to the `lupu` group

---

## Task 3: Create the `Hupu` System User
![](https://github.com/FawazSalman/linux-management/blob/main/task1/images/task_three.png)
I created a system user `hupu` with a disabled login shell:
```bash
sudo useradd --system --shell /bin/false hupu
```
- `--system`: Creates a system account
- `--shell /bin/false`: Prevents user login

---

## Task 4: Add `Tupu` and `Lupu` to Sudo Users
I provided `sudo` privileges to both users using the following method:

### Using `visudo`
```bash
sudo visudo
```
### Adding Users to the `sudo` Group
```bash
sudo usermod -aG sudo tupu
sudo usermod -aG sudo lupu
```
---

## Task 5: Create `/opt/projekti` and Assign Access
I created a shared directory `/opt/projekti` for both `tupu` and `lupu`, ensuring only they could access and modify files inside.
![](https://github.com/FawazSalman/linux-management/blob/main/task1/images/task_five.png)
### Steps to Accomplish the Task
1. **Create the directory**
   ```bash
   sudo mkdir /opt/projekti
   ```
2. **Create a shared group and add users**
   ```bash
   sudo groupadd projekti
   sudo usermod -aG projekti tupu
   sudo usermod -aG projekti lupu
   ```
3. **Assign correct ownership**
   ```bash
   sudo chown tupu:lupu /opt/projekti
   ```
4. **Set permissions**
   ```bash
   sudo chmod 770 /opt/projekti
   sudo chmod g+s /opt/projekti
   ```

### Explanation
- The **projekti group** ensures that both users (`tupu` and `lupu`) have access.
- `chown tupu:lupu /opt/projekti` sets the ownership and to the users `tupu` and `lupu`.
- `chmod 770` ensures **only** the owner and group members can access the directory.
- `chmod g+s` ensures that any new files inside inherit the `projekti` group ownership.

### Verification
Run:
```bash
ls -ld /opt/projekti
```
Expected output:
```
drwxrws--- 2 root projekti 4096 Jan 26 20:52 /opt/projekti
```

---



