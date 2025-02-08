## 🌐 **Network Printer Connectivity Issues**
### **Step 1: Check Wired or Wireless Connection**
- For wired printers:
  - Ensure the **Ethernet cable** is securely connected to both the **printer** and the **network port**.
  - If the printer has an **RJ45 port**, verify the network connection.
- For wireless printers:
  - Check that the printer is connected to the **correct Wi-Fi network (SSID)**.
  - Ensure the printer is within **range of the wireless access point**.
  - If the signal is weak, consider using a **wireless repeater** or moving the printer closer to the router.

### **Step 2: Verify Network Settings**
- Confirm that the printer has a **valid IP address**:
  - Use DHCP to assign an IP automatically.
  - Alternatively, assign a **static IP address** along with the correct **subnet mask, gateway, and DNS**.
- Run a **ping test** to verify connectivity:
```bash
ping <printer_IP_address>
```
- If the printer is still not detected, check firewall settings and **temporarily disable antivirus software** to rule out network security blocks.

### **Step 3: Print a Test Page**
- Use the **printer’s control panel** to print a test page.
- If the test page prints successfully, the issue lies with the **computer or network configuration**.
