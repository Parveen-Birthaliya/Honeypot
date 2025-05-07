##  Step 4: Log Analysis & Attack Insights

> Extract meaningful intelligence from raw honeypot logs using ELK stack capabilities. Learn how to detect patterns, attribute attacks, and build proactive defenses based on telemetry collected from T-Pot.

---

###  4.1 Log Sources Collected by T-Pot

T-Pot integrates multiple honeypots and services. Each container generates structured logs that are shipped to **Logstash → Elasticsearch → Kibana**.

| Source Honeypot | Container Name | Log Purpose                                     |
|------------------|----------------|-------------------------------------------------|
| Cowrie           | `cowrie`       | SSH/Telnet brute-force, session replays        |
| Dionaea          | `dionaea`      | Malware capture, SMB/HTTP/FTP attacks          |
| Mailoney         | `mailoney`     | SMTP spam honeypot logs                         |
| Conpot           | `conpot`       | Industrial/SCADA honeypot traffic               |
| Elasticsearch    | `elasticsearch`| Backend search database                         |
| Logstash         | `logstash`     | Log parsing, enrichment, transformation         |
| Suricata (opt)   | `suricata`     | Network-based IDS alerts (if configured)        |

---

### 🔍 4.2 Querying Logs in Kibana

Go to **Kibana > Discover**, select the `logstash-*` index pattern, and use Lucene/KQL syntax to filter logs.

#### 📌 Sample Queries:
```kql
# Find all brute-force SSH attempts
event.module: "cowrie" AND event.action: "login.failed"

# Filter Dionaea malware download attempts
event.module: "dionaea" AND event.type: "connection"

# Search for sessions from a specific IP
source.ip: "185.209.0.35"

# Filter activity based on honeypot name
host.name: "cowrie" OR host.name: "dionaea"
