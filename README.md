# T-Pot Honeypot Deployment on Vultr Cloud 🛡️

> Enterprise-ready Honeypot-as-a-Service with Real-Time Log Analysis

## 📌 Project Summary

**T-Pot** is an all-in-one multi-honeypot platform combining containers of popular honeypot daemons (e.g., Cowrie, Dionaea, Mailoney, and more) integrated with an ELK stack for real-time data visualization. This document details the secure deployment of T-Pot on Vultr Cloud and analysis of attack patterns.

---

## 📁 Table of Contents

- [Requirements](#requirements)
- [Step 1: Cloud Provisioning (Vultr)](#step-1-cloud-provisioning-vultr)
- [Step 2: Installing T-Pot Honeypot](#step-2-installing-t-pot-honeypot)
- [Step 3: Accessing Kibana Dashboard](#step-4-accessing-kibana-dashboard)
- [Step 4: Log Analysis & Attack Insights](#step-5-log-analysis--attack-insights)
- [Step 5: Hardening & Monitoring](#step-6-hardening--monitoring)
- [Learning Outcomes](#learning-outcomes)
- [References](#references)

---

## ✅ Requirements

- Vultr account ([Sign up](https://www.vultr.com/?ref=8674334-6G))
- 1 VM (Recommended: Ubuntu 20.04 LTS, 8 GB RAM, 100 GB SSD, 1 IPv4)
- Static IP (Auto-assigned by Vultr)
- Domain (Optional) for remote access
- SSH client (e.g., OpenSSH, PuTTY)
- Git, Docker knowledge preferred

---

## 🛰️ Step 1: Cloud Provisioning (Vultr)

1. **Login to Vultr Dashboard**
2. Deploy a **Compute Instance**
   - OS: Ubuntu 20.04 x64
   - Server Type: Shared cloud
   - Region: Prefer region near you
   - IPv4: Enabled
3. Choose:
   - RAM: Minimum 8 GB
   - Storage: 100 GB SSD
   - I choosed (8Gb ,160GB SSD , 4 cores)
5. Click **Deploy Now**
6. Once deployed, get the **IP Address** and set up SSH:
   ```bash
   ssh root@<your-server-ip>
   ```
