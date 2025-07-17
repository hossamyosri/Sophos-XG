# Sophos XG Firewall Deployment – Real-World Scenario 🛡️

## 📌 Overview

This repository documents a practical deployment and configuration of a **Sophos XG Firewall (SFOS 21)** in a real organization, designed to secure and segment network access across multiple user groups, applying granular policies for security, access control, and performance.

> ⚠️ **Note**: All sensitive data and real IPs have been obfuscated to preserve organizational confidentiality.

---

## 🧠 Objectives

* Implement a secure, policy-based environment using Sophos XG
* Segment internal network access by user roles/devices
* Protect against external and internal cyber threats
* Apply Application and Web Filtering Rules
* Create firewall rule groups based on MAC addresses
* Control and monitor network activity through reporting and logging

---

## 🏗️ Network Design Summary

* LAN interface configured with IP: `172.168.5.1`
* WiFi network connected to Sophos and treated as the default gateway
* Users connected via Ethernet (PCs) and WiFi (phones/laptops)
* Goal: Apply policies **only to PCs/users** while exempting WiFi-connected personal devices

### 🧱 Implementation Highlights:

* VLAN not used due to router limitations
* Segregation achieved by **creating MAC Address groups**
* Devices grouped and identified manually
* Firewall Rules applied to device groups (MAC-based)

---

## 🔐 Security Features & Policy Breakdown

### 🔹 1. Web Filtering Policy

**Purpose**: Block access to adult, streaming, gambling, and time-wasting websites during work hours.

* **Category filters**: Social Networking, Adult Content, Ads, Video & Streaming
* **File types blocked**: `.exe`, `.torrent`, `.mp4`, `.zip` (based on risk level)
* Applied quota: e.g., YouTube = 30 min/day, auto block after limit
* Schedule: Enforced from 9AM–5PM

### 🔹 2. Application Control Policy

**Purpose**: Block or limit applications that affect productivity or security.

* Blocked Apps: BitTorrent, Psiphon, Telegram Desktop, Zoom (upload only)
* Throttled: Google Drive Uploads, Dropbox Sync
* Allowed: Outlook, Teams, SAP
* Detection using deep-packet inspection (DPI Engine)

### 🔹 3. MAC Address Grouping

**Purpose**: Target specific users/devices for policy enforcement

* Created multiple groups:

  * `Staff-PCs`
  * `Management`
  * `Personal Devices`
* Each firewall/web/app policy tied to specific MAC group
* Example: Staff-PCs → Strictest policy

### 🔹 4. Captive Portal (Optional)

* Enabled user-based login for visitors
* Phone number or Username login method tested

### 🔹 5. Routing & Segmentation

**Scenario**: 3 floors, different teams per floor

* Each floor connected via unmanaged switch
* Core switch connected to Sophos
* IP Ranges:

  * Staff Range: `172.168.5.0/24`
  * Visitors/WiFi: `172.168.9.0/24`
* Routing handled by Sophos with Zone segmentation

---

## 📈 Monitoring & Logs

* Enabled reporting dashboard
* Scheduled daily reports via email
* Live logs for Application & Web Filtering enabled
* Real-time alerts for policy violations

---

## 📁 Repository Structure

```
├── README.md
├── policies/
│   ├── web-control.md
│   ├── app-control.md
│   └── firewall-rules.json
├── images/
│   ├── dashboard.png
│   ├── network-diagram.png
│   └── rule-example.png
```

---

## 📸 Diagrams & Visuals

* 🔹 Dashboard overview screenshot
* 🔹 Firewall Rule example with source/destination/MAC groups
* 🔹 Full Network Diagram (multi-floor setup)

> 🖼️ See `/images` folder for visuals (all mockups or sanitized)

---

## 🧠 Lessons Learned

* MAC-based filtering can be powerful where VLANs aren't available
* Sophos Firewall policies are highly customizable per group or device
* DPI Engine + Application Control = High visibility & strong security
* Captive Portal is useful for guest or temporary access control

---

## ✅ Technologies Used

* Sophos XG Firewall v21
* Unmanaged TP-Link Switches
* TP-Link / WE Routers (Bridged Mode)
* Local LAN on `172.168.X.X`

---

## 🧑‍💻 Author

**Hossam Yosri**
IT Specialist • Network Security & Systems Admin Enthusiast
[LinkedIn](https://www.linkedin.com/in/hossamyosri) • [GitHub](https://github.com/hossamyosri)

> 📬 For collaborations or more advanced setups: [hossamyousry907@gmail.com](mailto:hossamyousry907@gmail.com)
