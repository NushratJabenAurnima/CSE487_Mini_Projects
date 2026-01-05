# 🔐 Mini Project 1 — PKI & TLS (HTTPS) Security Implementation

This project demonstrates the secure deployment of a networked web system using **Public Key Infrastructure (PKI)** and **Transport Layer Security (TLS)** to enable **HTTPS** for a custom domain (`www.verysecureserver.com`).

The project focuses on building a trusted PKI hierarchy, configuring secure HTTPS communication, applying basic network hardening, enabling intrusion detection, and validating encrypted traffic.

---

## 🎯 Project Objectives
- Design and implement a complete **PKI trust hierarchy** (Root CA → Intermediate CA → Server Certificate)
- Enable **HTTPS (TLS)** on Apache/XAMPP using a valid certificate chain
- Configure **DNS resolution** for a custom domain using `bind9`
- Apply **network hardening** using UFW firewall rules
- Enable **Intrusion Detection System (IDS)** monitoring using Snort
- Validate encrypted communication using browser tools and Wireshark
- Demonstrate **certificate revocation** and trust enforcement

---

## 🛠️ Implementation Overview

### 🔑 PKI Setup (OpenSSL)
- Created a Root Certificate Authority (CA)
- Created an Intermediate/Sub CA signed by the Root CA
- Generated server private key and Certificate Signing Request (CSR)
- Signed the server certificate using the Intermediate CA
- Built and verified the complete certificate chain  
  ![Certificate Chain Verification](./Certificate%20chain%20verification.png)

---

### 🌐 HTTPS Configuration (Apache/XAMPP)
- Enabled SSL/TLS modules
- Configured Apache to use the server certificate, private key, and CA chain
- Verified secure HTTPS access via browser  
  ![Browser HTTPS Padlock](./Browser%20HTTPS%20padlock.png)

---

### 🧭 DNS Configuration (bind9)
- Configured forward DNS zone for `www.verysecureserver.com`
- Verified domain resolution using `nslookup` / `dig`  
 ![DNS Resolution](./DNS%20resolution%20output.png)

---

### 🔥 Firewall Hardening (UFW)
- Set default deny policy for incoming traffic
- Allowed only essential inbound ports:
  - **53** (DNS)
  - **80** (HTTP)
  - **443** (HTTPS)
- Verified firewall rules using `ufw status`  
---

### 🚨 Intrusion Detection System (Snort)
- Configured `HOME_NET`
- Enabled alert logging
- Implemented and tested a basic local Snort rule  
---

## 🔍 Security Validation
- Inspected certificate details and trust chain in browser
- Captured TLS handshake and verified encrypted application data using Wireshark  
![Browser HTTPS Padlock](./Browser%20HTTPS%20padlock.png)
- Revoked the server certificate and confirmed trust failure in browser  
---

## 🧰 Tools & Environment
- Ubuntu (Virtual Machine)
- OpenSSL
- Apache / XAMPP
- bind9
- UFW
- Snort
- Wireshark
- Firefox / Chromium

---

## ✅ Verification Checklist
- [x] Domain resolves correctly via DNS
- [x] HTTPS loads with a valid TLS certificate
- [x] Certificate chain verified (Server → Intermediate → Root)
- [x] Firewall restricts inbound traffic to required ports only
- [x] Snort generates alerts for defined rules
- [x] TLS traffic confirmed as encrypted in Wireshark
- [x] Certificate revocation invalidates trust successfully

---

## 👥 Collaboration
- Nusrat Jaben Aurnima  
- Zihad Khan  
- Shairin Akter Hashi  
- Tahmina Ahmed  
- MD Shahrukh Hossain Shihab  

---

## 🔒 Security Notice
Private keys, passphrases, and sensitive certificate materials are **not included** in this repository.  
All secret files (e.g., `*.key`) are excluded using `.gitignore` and stored securely offline.

---

## 📌 Notes
This project is intended for **educational and academic purposes** to demonstrate foundational concepts of PKI, TLS, and secure web communication.
