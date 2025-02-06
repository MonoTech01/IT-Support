# 🚀 Switch Firmware Upgrade Guide  

## 📌 Step-by-Step Process  

### **Step 1: Connect Your Switch to Your Computer**  
- Use a **console cable** to connect your switch to your computer.  
- Open **Device Manager** on your computer and check the **Ports (COM & LPT)** section to determine the correct COM port.  

### **Step 2: Open a Terminal Session with Putty**  
- Open **Putty** and select the following options:  
  - **Connection type**: Serial  
  - **Serial line**: COM[number] (e.g., COM3)  
  - **Speed**: [Baud rate] (default: 9600, recommendation: 38400)  
- Click **Open** to access the command-line interface (CLI) of the switch.  

---

### **Step 3: Set Up VLAN Management and IP Address** in CLI 
- Configure the **management VLAN** and assign an IP address.  
- Associate a port to the VLAN by **untagging** that port (i.e., access port).  
  - **An untagged port = access port** (associated with only one VLAN, not a trunk port).  

Use the management IP address you just set up to access the **switch's GUI** by copying and pasting it into a web browser.  

---

### **Step 4: Locate and Upload the Firmware via GUI**  
- In the GUI, navigate to:  
  - **System -> Firmware**  
- **Find and download the correct firmware** from the official website of your switch brand.  
  - Example: Aruba firmware is available on [HPE Networking Support](https://networkingsupport.hpe.com/).  
- Upload the firmware in the GUI interface.  
- Run `show flash` in CLI to confirm the firmware is uploaded.  
- **Always upgrade the primary firmware first** before upgrading the secondary (backup) firmware.  
  - If the new firmware fails, you can revert to the backup.  

---

### **Step 5: Upgrade Firmware via CLI (Alternative to GUI)**  
If the **web GUI is unresponsive due to outdated software**, use **FTP or TFTP** to upgrade the firmware:  

1. **Verify firmware version and flash memory:**  
```cisco
show version
show flash
```  

2. **Ping the TFTP/FTP server to ensure connectivity:**  
```cisco
ping <FTP/TFTP_Server_IP>
```  

3. **Find your device’s IP address running the TFTP/FTP server:**  
```bash
ipconfig /all
```

4. **Transfer firmware from TFTP/FTP server to switch flash memory:**  
   - **TFTP Method:**  
```cisco
copy tftp flash <TFTP_Server_IP> <Firmware_File_Name> primary/secondary
```
   - **FTP Method:**  
```cisco
copy ftp flash <FTP_Server_IP> <Firmware_File_Name> primary/secondary
```
**Example:**  
```cisco
copy ftp flash 192.168.1.100 ArubaOS_XX.XX.X.swi primary
```

---

### **Step 6: Reboot the Switch**  
After the firmware transfer is complete, reboot the switch:  
```cisco
reload
```  

Confirm **Yes** to proceed with the upgrade.  

---

### **Step 7: Verify and Upgrade Backup Firmware**  
- Check `show flash` to confirm the new version.  
- If the new firmware is functioning correctly, proceed with upgrading the backup firmware using the same method.  

---

### **Step 8: Save Configuration**  
Ensure the configuration is saved to prevent rollback:  
```cisco
write memory
```
✅ **Firmware upgrade completed successfully!** 🚀  

---

## ⚠️ **Troubleshooting Tips**  
- **Ping Fails?** Disable the firewall on the device running the FTP/TFTP server.  
- **TFTP/FTP Transfer Fails?** Verify the file name and path, ensure the FTP/TFTP server is running, and check for connectivity.  
- **Switch Doesn’t Boot Correctly?** Try using the **secondary firmware slot** during the transfer.  

---

## 💡 **Additional Notes**  
- **Primary vs. Secondary Flash Slots:** Aruba switches allow firmware upgrades to **primary or secondary flash slots**.  
- **Always Verify Firmware Compatibility**: Ensure the firmware version matches your switch model to prevent issues.  
- **Backup Configuration Before Upgrading**: Use `copy running-config startup-config` before performing any upgrade.  
