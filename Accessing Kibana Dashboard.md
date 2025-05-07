## 📊 Step 3: Accessing the Kibana Dashboard

> Gain real-time visibility into honeypot telemetry using the ELK-powered Kibana interface.

---
## Access Tpot Server
```bash
ssh honeypot@your-server-ip -p 64295
```
Provide Password you set during adding user to the server

### 🔐 3.1 Authentication Credentials

After a successful T-Pot installation, the Kibana interface is secured via HTTPS and protected with the username/password configured during the setup process.

- **Username:** `your_user` *(set during install)*
- **Password:** `your_password` *(set during install)*

Ensure that the required ports are open in the server's firewall (`64297` by default).

---

### 🌐 3.2 Access URL

Open the following URL in your web browser:

```url
https://<your-server-ip>:64297
```
- **Provide you web username and password in the popup**
- **Click on the Kibana** : Now you have access to kibana
