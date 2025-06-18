# 🛡️ Phishing Simulation using SET (Social-Engineer Toolkit)

![image](https://github.com/user-attachments/assets/c782714e-6743-4557-a7db-77249a8c2d1f)


## 🎯 Objective
Simulate a phishing attack using the **Credential Harvester** method from the **Social-Engineer Toolkit (SET)** on Kali Linux in a controlled lab environment. This red team exercise demonstrates how web-based phishing campaigns can be conducted and logged for educational and awareness purposes.

---

## ⚙️ Tools & Lab Environment

- **Attacker Machine:** Kali Linux VM (UTM-based)
- **Victim Machine:** Windows 10 VM (Azure-hosted)
- **Network Configuration:** Both VMs configured on the same subnet (192.168.64.0/24)
- **Phishing Tool:** Social-Engineer Toolkit (SET)
- **Web Server:** Apache2 (default port 80)
- **Monitoring:** Manual log analysis + screenshots
- **Target Site:** `http://example.com` (test site clone)

---

## 🛠️ Step-by-Step Setup

### 1️⃣ SET Configuration

Launch SET and begin your phishing configuration:

```bash
sudo setoolkit
```

# Navigate the menu as follows:

```bash
1) Social Engineering Attacks
2) Website Attack Vectors
3) Credential Harvester Attack Method
2) Site Cloner
```

# When prompted, enter the URL to clone:

```bash
http://example.com
```
This will clone the login interface and host it on your Kali box.

### 2️⃣ Apache Service (Start Web Server)
Make sure the web server is up and running:

```bash
sudo systemctl start apache2
```

### 3️⃣ Victim Access
On your Windows VM, open a web browser and navigate to your Kali’s IP address:

```bash
http://192.168.64.5
```

💡 To find your Kali IP address:

```bash
ip a
```
Look for something like inet 192.168.64.5 under eth0 or similar.

### 4️⃣ Credential Capture
Once the victim enters their credentials on the cloned page, SET captures the input.

To view the captured data:

```bash
cd /root/.set/reports
ls
```

Locate the folder with the timestamp of your attack.

Example:

```basH
cd '2025-06-18 10:11:47'
cat harvester.txt
```

📝 You should see the captured username and password entries in plain text or XML format.

### 🧪 Attack Details

| **Component**       | **Details**                                                |
|---------------------|-------------------------------------------------------------|
| Technique           | Credential Harvester via cloned login form                 |
| Phishing Vector     | Web-based phishing (victim voluntarily enters credentials) |
| Target              | Windows VM via browser                                     |
| Result              | Username/password harvested to SET logs                    |

<img width="674" alt="Screenshot 2025-06-18 at 1 01 50 PM" src="https://github.com/user-attachments/assets/74da36bb-37d9-4d54-a5c0-a8d66ac0af64" />
<img width="708" alt="Screenshot 2025-06-18 at 1 02 24 PM" src="https://github.com/user-attachments/assets/18a2b268-8a24-4d11-8f8e-17d50883c46f" />
<img width="632" alt="Screenshot 2025-06-18 at 11 42 55 AM" src="https://github.com/user-attachments/assets/24b29c9b-89ce-4dbc-aabf-d6310131d4d8" />


---

### 📈 Lessons Learned

- 🔒 Public-facing web applications must be secured and validated to prevent cloning attacks.  
- 🧠 Phishing simulations are valuable training tools to understand social engineering.  
- 🎯 Even technically aware users can fall for legitimate-looking phishing pages.  
- 🛡️ Endpoint tools like Microsoft Defender can help flag suspicious URLs or unusual login activity — visibility matters.

---

### 🚧 Legal & Ethical Disclaimer

> 🛑 This simulation was performed in a fully controlled lab environment for educational and ethical research purposes **only**.  
> Do **not** use these tools or techniques outside of environments where you have **explicit permission**.

### 🔗 Related Skills

- ✅ **Red Team Operations**
- ✅ **Social Engineering Tactics**
- ✅ **Kali Linux Proficiency**
- ✅ **Apache & Networking Basics**
- ✅ **Cybersecurity Awareness**
- ✅ **Log Analysis & Threat Detection**


### 🙌 Credits

Big thanks to the open-source community behind SET and cybersecurity educators helping people learn offensive security skills the right way.

