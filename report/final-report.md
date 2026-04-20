# Final Report – SOC Home Lab Investigation

## Lab Architecture

The environment consisted of three main systems:

* **Attacker Machine (Ubuntu-Desktop):** Used to generate network-based attacks
* **Victim Machine (Windows 10):** Monitored using Sysmon and Suricata
* **SIEM Server (Ubuntu-server):** Running Wazuh for centralized log collection and analysis

All logs were forwarded to Wazuh for investigation.

---

## Data Sources

### Network Monitoring – Suricata

Suricata was deployed on the Windows host to monitor network traffic and detect suspicious patterns such as scanning activity.

* Log file: `eve.json`
* Detection: Network scan (Nmap)

---

### Endpoint Monitoring – Sysmon

Sysmon was used to capture detailed system activity, particularly process and creation events.

* Event ID: 1 & 4688 (Process Creation)
* Focus: Execution of PowerShell

---

### Log Aggregation – Wazuh

Wazuh centralized logs from both souces, Suricata and Sysmon, enabling unified analysis.

---

## Attack Scenario

The simulated attack consisted of two stages:

1. **Reconnaissance:**
   An Nmap SYN scan was executed from the attacker machine targeting the Windows host.

2. **Execution:**
   A PowerShell instance was launched on the victim machine.

This scenario simulates the initial phases of an attack's life cycle.

---

## Investigation Process

### Step 1 – Identify Network Activity

Suricata logs were reviewed in Wazuh, revealing alerts indicating scanning behavior originating from the attacker IP.

Key observations:

* Multiple ports targeted
* Quick connection attempts
* Classification as a scanning activity

---

### Step 2 – Identify Endpoint Activity

Sysmon logs were analyzed to detect process execution events.

Key findings:

* Execution of `powershell.exe`
* Happened on the same host targeted by the scan
* Proximity in time to the network event

---

### Step 3 – Correlate Events

Manual correlation was performed based on:

* Timestamp proximity
* Source and destination IPs
* Host consistency

The events were determined to be related due to their temporal and contextual alignment.

---

## Analysis & Findings

The combination of:

* Network scanning activity
* PowerShell execution

suggests a potential attack sequence involving reconnaissance followed by execution.

While each event alone may not be malicious, together they increase the likelihood of suspicious behavior.

---

## MITRE ATT&CK Mapping

* **T1046 – Network Service Discovery**
* **T1059.001 – PowerShell**

These techniques are commonly observed in reconnaissance and execution phases of attacks.

---

## Recommendations

To improve detection and analysis capabilities:

1. Implement automated correlation rules in Wazuh
2. Enable command-line logging in Sysmon for deeper visibility
3. Integrate threat intelligence feeds for IP reputation analysis
4. Expand monitoring to include authentication logs
5. Develop dashboards for faster incident triage

---


## Conclusion

This lab demonstrates the importance of correlating multiple data sources to identify potentially malicious behavior.

By combining network and endpoint logs, it is possible to detect patterns that would otherwise go unnoticed when analyzing logs in isolation.

The skills demonstrated in this project align with real-world SOC analyst responsibilities, including log analysis, event correlation, and threat identification.
