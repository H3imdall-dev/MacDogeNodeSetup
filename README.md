![Macintosh Doge Node Setup](https://github.com/user-attachments/assets/e5e13a0a-a562-41e7-80eb-e48176ce9044)


# **Dogecoin Node Setup on macOS 🚀**
*A step-by-step guide to setting up a Dogecoin node on a macOS machine.*

---

## **🛠️ System Requirements**
- **Minimum Specs:**
  - 4 CPU Cores
  - 220+ GB Storage
  - macOS Mojave (10.14) or later

---

## **📡 Router Configuration (Port Forwarding & Static IP)**
To allow your Dogecoin node to communicate properly with the network, follow these steps:

### **Step 1: Log into Your Router**
1. Open a web browser and go to:
   ```
   192.168.0.1
   ```
2. Log in to your router (default credentials are usually on a label on the router).

### **Step 2: Assign a Static IP**
1. Navigate to **DHCP Settings**.
2. Locate your Mac in the connected devices list.
3. Assign it a **static IP address**, e.g.:
   ```
   eg 192.168.0.24 make your own  
   ```
4. **Remember this IP**, as you will need it later.

### **Step 3: Open Port 22556**
1. Go to **Port Forwarding** settings.
2. Create a new rule:
   - **Internal IP:** *(Your static IP from Step 2)*
   - **Port:** `22555` (start) `22556` (end)
   - **Protocol:** **Both (TCP & UDP)**
   - **Enable the rule**

✅ **Done!** Your router is now configured for Dogecoin node communication.

---

## **🛠️ Installing Dogecoin Core on macOS**

### **Step 1: Download & Install Dogecoin Core**
1. Go to the official **Dogecoin Core** release page:
   📥 **[Dogecoin Core Releases](https://github.com/dogecoin/dogecoin/releases/latest)**
2. Download the latest macOS release (`dogecoin-<version>-osx.dmg`).
3. Open the `.dmg` file and drag **Dogecoin Core** into the Applications folder.
4. Open **Dogecoin Core** from Launchpad.
5. Allow the node to **run for 1 minute** to initialize the necessary files.
6. Close Dogecoin Core completely.

### **Step 2: Configure Dogecoin Core**
1. Open **Finder**, then go to:
   ```
   ~/Library/Application Support/Dogecoin/
   ```
2. Right-click inside the folder and create a new text file named:
   ```
   dogecoin.conf
   ```
3. **Copy & paste** the following configuration (modify username/password/IP)(added txindex incase you want to do other developments or indexing:
   ```ini
   rpcuser=your_username
   rpcpassword=your_password
   rpcallowip=127.0.0.1
   maxconnections=50
   rpcport=22555
   txindex=1
   server=1
   ```
4. **Save and close** the file.
5. Restart **Dogecoin Core** and allow it to sync completely (this may take several hours).

---

## **🔍 Verifying Node Status**
To check your node's sync progress, open **Terminal** and run:
```bash
/Applications/Dogecoin-Qt.app/Contents/MacOS/dogecoin-cli getblockcount
```
- This will show the **current block count** and indicate syncing progress.

To check active connections:
```bash
/Applications/Dogecoin-Qt.app/Contents/MacOS/dogecoin-cli getconnectioncount
```
- If **connections = 8**, your **port forwarding may be incorrect**.

---

## **🛠️ Setting Dogecoin Core to Run on Startup**
To ensure your node runs automatically:
1. Open **System Preferences** → **Users & Groups**.
2. Click the **Login Items** tab.
3. Click **+**, then select **Dogecoin Core** from the Applications folder.
4. Click **Add**.

✅ **Your node will now start automatically when you log in!**

---

## **🚀 Summary**
### **✔️ What We Did:**
- Configured **Router Port Forwarding & Static IP**
- Downloaded & Installed **Dogecoin Core**
- Configured **dogecoin.conf**
- Started the **Dogecoin Node**
- Verified **Sync & Connections**
- Set **Dogecoin Core to Run on Startup**

💚 **You now have a fully functional Dogecoin Node on macOS!** 🐶🚀  

---

## **🙋 Need Help?**
If you have any issues, feel free to **open an issue** or reach out to the **@Heimdall_Bull** on X! 🐕✨  

---
🚀 **Happy Mining & Supporting the Dogecoin Network!** 🐶

