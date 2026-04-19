# SOC Home Lab – Threat Detection with Wazuh, Suricata and Sysmon

## Overview
This project simulates a basic SOC environment using:
- Wazuh SIEM
- Suricata IDS
- Sysmon for endpoint monitoring

The goal is to detect suspicious activity by analyzing logs from multiple sources.

---

## Lab Architecture

Attacker (Ubuntu)\
        |\
        v\
Windows 10 (Sysmon + Suricata + Wazuh Agent)\
        |\
        v\
Wazuh Server (Ubuntu)

---

## Data Sources

### Network Detection
- Suricata IDS
- Rule ID: 86601

### Endpoint Detection
- Sysmon
- Windows Event Logs

---

## Attack Scenario

1. Nmap scan from attacker
2. PowerShell execution on victim
3. Log analysis in Wazuh

---

## Detection Approach

Detection was performed manually by correlating:

- Suricata alerts (network activity)
- Sysmon logs (process execution)

---

## Results

The analysis showed:

- Network scanning activity from attacker IP
- PowerShell execution on target machine

This behavior may indicate early stages of compromise.

---

## MITRE ATT&CK Mapping

- T1046 – Network Service Discovery
- T1059 – Command Execution
