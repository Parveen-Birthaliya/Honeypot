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
type: cowrie and eventid: cowrie.login.failed

# Filter Dionaea malware download attempts
type: dionaea and connection.type: accept

# Search for sessions from a specific IP
src_ip:41.138.161.118

# Filter activity based on honeypot name
type: "cowrie" OR type: "dionaea"
```
### 4.3 Kibana Dashboard Analysis
![Kibana Dashboard](https://github.com/Parveen-Birthaliya/Honeypot/blob/main/images/DashBoard.png)

#### 4.3.1 Attack Distribution
![Attack Distribution](https://github.com/Parveen-Birthaliya/Honeypot/blob/main/images/AttackDist.png)
**Bar Chart**
![Bar Chart](https://github.com/Parveen-Birthaliya/Honeypot/blob/main/images/AttackDistBarchart.png)

#### 4.3.2 Attack by Country and Port



<p align="center">
  <img src="https://github.com/Parveen-Birthaliya/Honeypot/blob/main/images/PieChartCountryPort.png" width="60%" />
  <img src="https://github.com/Parveen-Birthaliya/Honeypot/blob/main/images/AttackByCountry.png" width="35%" />
</p>
