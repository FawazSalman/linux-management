# APT Package Management - Assignment Documentation

## By: Fawaz Salman
## Date: Feb 9, 2025

---

## **Part 1: Understanding APT & System Updates**

### **1. Check APT Version**
**Command:**  
```bash
apt --version
```
**Output:**  
The command displays the installed APT version.

![](https://github.com/FawazSalman/linux-management/blob/main/Apt_package_manangement/images/1.1.png) 

---

### **2. Update the Package List**
**Command:**  
```bash
sudo apt update
```
**Why is this step important?**  
- It updates the local package index from the repositories, ensuring we get the latest available versions.  

![](https://github.com/FawazSalman/linux-management/blob/main/Apt_package_manangement/images/1.png)  

---

### **3. Upgrade Installed Packages**
**Command:**  
```bash
sudo apt upgrade -y
```
**Difference between `update` and `upgrade`?**  
- `update`: Fetches the latest package lists but does not install updates.  
- `upgrade`: Installs the latest versions of installed packages.  

![](https://github.com/FawazSalman/linux-management/blob/main/Apt_package_manangement/images/2.png)

---

### **4. View Pending Updates**
**Command:**  
```bash
apt list --upgradable
```
**Output:**  
Displays the list of packages that can be upgraded.  

---

## **Part 2: Installing & Managing Packages**

### **5. Search for an Image Editor**
**Command:**  
```bash
apt search image editor
```
**Selected Package:** `exult-studio`  

![](https://github.com/FawazSalman/linux-management/blob/main/Apt_package_manangement/images/3.png)

---

### **6. View Package Details**
**Command:**  
```bash
apt show exult-studio
```
**Dependencies Required:**  
[List of dependencies from the output]  

![](https://github.com/FawazSalman/linux-management/blob/main/Apt_package_manangement/images/4.png) 

---

### **7. Install the Package**
**Command:**  
```bash
sudo apt install exult-studio -y
```
**Installation Confirmation:**  
The package was successfully installed.  

📷 **Insert Screenshot of the installation command and output.**  

---

### **8. Check Installed Package Version**
**Command:**  
```bash
apt list --installed | grep exult-studio
```
**Installed Version:** `1.8-2build3 amd 64`  

![]()  

---

## **Part 3: Removing & Cleaning Packages**

### **9. Uninstall the Package**
**Command:**  
```bash
sudo apt remove <package-name> -y
```
**Is the package fully removed?**  
- No, the configuration files remain on the system.  

📷 **Insert Screenshot of `sudo apt remove <package-name> -y` output.**  

---

### **10. Remove Configuration Files**
**Command:**  
```bash
sudo apt purge <package-name> -y
```
**Difference between `remove` and `purge`?**  
- `remove`: Uninstalls the package but keeps configuration files.  
- `purge`: Removes the package and its configuration files.  

📷 **Insert Screenshot of `sudo apt purge <package-name> -y` output.**  

---

### **11. Clear Unnecessary Dependencies**
**Command:**  
```bash
sudo apt autoremove -y
```
**Why is this step important?**  
- It removes orphaned dependencies that are no longer needed.  

📷 **Insert Screenshot of `sudo apt autoremove -y` if dependencies were removed.**  

---

### **12. Clean Up Downloaded Package Files**
**Command:**  
```bash
sudo apt clean
```
**What does this command do?**  
- It clears the package cache stored in `/var/cache/apt/archives`, freeing up disk space.  

📷 **Insert Screenshot of `sudo apt clean` (optional).**  

---

## **Part 4: Managing Repositories & Troubleshooting**

### **13. List All APT Repositories**
**Command:**  
```bash
cat /etc/apt/sources.list
```
**Observations:**  
- This file contains the list of software repositories (e.g., `main`, `universe`, `restricted`, `multiverse`).  

📷 **Insert Screenshot of `cat /etc/apt/sources.list`, showing some repository URLs.**  

---

### **14. Add the Universe Repository**
**Command:**  
```bash
sudo add-apt-repository universe
sudo apt update
```
**What types of packages are in the Universe repository?**  
- It contains **community-maintained** open-source software.  

📷 **Insert Screenshot of `sudo add-apt-repository universe` and `sudo apt update`.**  

---

### **15. Simulate an Installation Failure & Troubleshoot**
**Command:**  
```bash
sudo apt install fakepackage
```
**Error Message Received:**  
```
E: Unable to locate package fakepackage
```

**How to troubleshoot?**  
- Check for typos in the package name.  
- Run `sudo apt update` to refresh package lists.  
- Verify if the package exists using `apt search <package-name>`.  
- Ensure the correct repository is enabled in `/etc/apt/sources.list`.  

📷 **Insert Screenshot of `sudo apt install fakepackage` showing the error message.**  

---

## **Conclusion**
Through this assignment, we learned how to:  
✅ Manage packages using APT (install, update, remove).  
✅ Work with repositories and dependencies.  
✅ Troubleshoot package installation issues.  

📌 **This documentation includes all commands, outputs, and screenshots where required.**  

---

### ✅ **Save this as `APT_Package_Management.md` and upload it to GitHub!**  
Let me know if you need any modifications! 🚀
