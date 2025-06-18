# 🎣 Phishing Simulation Using SET

## 🔍 About This Project

This project demonstrates a hands-on **red team phishing simulation** using the **Social-Engineer Toolkit (SET)** inside a controlled lab environment. It replicates a realistic credential-harvesting phishing attack to understand attacker methodology, improve security awareness, and build red team skillsets.

### 💻 Environment Setup

- **Kali Linux VM** (attacker system)
- **Windows 10 VM** (victim system)
- **Host machine** for support and observation

All machines were isolated and configured for internal communication.

---

## 🎯 Objective

The goal of this simulation is to:

- Clone a legitimate-looking login page
- Harvest credentials through a phishing campaign
- Analyze log data to understand the attack path
- Strengthen red team and social engineering knowledge
- Explore detection and response strategies using endpoint tools like Microsoft Defender

---

## 💬 This is what I did... 

> _"I performed a phishing simulation using the Social-Engineer Toolkit to better understand how attackers trick users into submitting credentials via realistic-looking login pages. Using a Windows VM to represent the victim, I accessed the cloned site and captured login data in real time. This helped me learn how these attacks happen and why strong detection tools, network protections, and user training are critical for cybersecurity."_  

---

### 🧠 Real-World Application: How Cloned Sites Work in the Wild

In real-world phishing campaigns, attackers often:

- **Clone a high-traffic, trusted website** (like a bank login page or corporate SSO portal).
- **Host the fake page** on a domain that looks similar (e.g., `g00gle.com` instead of `google.com`).
- **Send out emails or messages** tricking users into clicking the link (this could be from a spoofed email address or a compromised account).
- Once the **victim enters credentials**, the attacker captures the data instantly and may:
  - Use them for immediate access (e.g., logging into email, corporate VPN, or cloud services).
  - Sell the credentials on the dark web.
  - Launch further attacks, such as internal phishing or privilege escalation within an organization.

This simulation mimics the **technical side** of how these cloned sites are deployed, hosted, and used to **harvest sensitive user input**.

> ⚠️ It’s a common method used in real breaches — especially when **two-factor authentication (2FA)** is not enforced.
