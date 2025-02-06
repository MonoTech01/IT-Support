# 🚀 Switch Firmware Upgrade with TFTP Guide

## 📌 Step-by-Step Process  

### **Step 1: Download a TFTP Server**  
To transfer the firmware, download and install a **TFTP server**. Some free options include:  
- **[Tftpd64](http://tftpd32.jounin.net/tftpd32.html)**  
- **[SolarWinds TFTP Server](https://www.solarwinds.com/free-tools/free-tftp-server)**  

---

### **Step 2: Configure the TFTP Server**  
- Set up the **file path** where firmware files will be stored.  
- Adjust security settings as needed.  
- Copy and paste the necessary firmware file into the designated **TFTP folder**.  

---

### **Step 3: Power On the Switch**  
Check your switch **firmware version** and **flash memory** using:  
```
show version
show flash
```  

---

### **Step 4: Verify Connectivity to the TFTP Server**  
- Use your Aruba switch to **ping the TFTP server**.  
- If the ping fails, **disable the firewall** on the device running the TFTP service.  
```
ping <TFTP_Server_IP>
```  

---

### **Step 5: Find the Device’s IP Address**  
On the system running the TFTP server, open **Command Prompt** and run:  
```bash
ipconfig /all
```
- Locate the **IPv4 address** of the device.  
- This **device’s IP address = TFTP server address**.  
- **Copy this IP address** for the next step.  

---

### **Step 6: Transfer the Firmware to the Switch**  
1. Enter **enable mode** (`en`) and **configuration mode** (`config`).  
2. Copy the firmware from the **TFTP server to the switch flash memory**:  
```
copy tftp flash <TFTP_Server_IP> <Firmware_File_Name> primary/secondary
```
**Example:**  
```cisco
copy tftp flash 192.168.1.100 ArubaOS_XX.XX.X.swi primary
```  

---

### **Step 7: Reboot the Switch**  
After the firmware transfer is complete, reboot the switch:  
```
reload
```  

---

### **Step 8: Save Configuration**  
Ensure the configuration is saved to prevent rollback:  
```
write memory
```
👌 **Firmware upgrade completed successfully!** 🚀  

---

## ⚠️ **Troubleshooting Tips**  
- **Ping Fails?** Disable the firewall on the device running the TFTP server.  
- **TFTP Transfer Fails?** Verify the file name and path, ensure the TFTP server is running, and check for connectivity.  
- **Switch Doesn’t Boot Correctly?** Try using the **secondary firmware slot** during the transfer.
  
---

## 💡 **Additional Notes**  
- **Primary vs. Secondary Flash Slots:** Aruba switches allow firmware upgrades to **primary or secondary flash slots**.  
- **Always Verify Firmware Compatibility**: Ensure the firmware version matches your switch model to prevent issues.  
- **Backup Configuration Before Upgrading**: Use `copy running-config startup-config` before performing any upgrade to ensure that current settings are saved and persist after the reboot.
