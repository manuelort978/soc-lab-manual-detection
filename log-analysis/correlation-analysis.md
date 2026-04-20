# Correlation Analysis – Multi-Source Investigation

## Data Sources Overview

### 1. Network Telemetry (Suricata)

Suricata provides visibility into network traffic and detects suspicious patterns such as scans, exploits, and anomalous connections.

Relevant event:

* **Rule ID:** 86601
* **Type:** Alert
* **Description:** Network scan detected (e.g., Nmap SYN scan)

---

### 2. Endpoint Telemetry (Sysmon)

Sysmon captures detailed system activity, including process creation and command execution.

Relevant event:

* **Event ID:** 1 (Process Creation)
* **Process:** powershell.exe
* **Host:** Windows 10 victim machine (192.168.56.105)

---

## Event Analysis

### Timeline Correlation

 Time (approx) | Event Source | Description                            \
 T0            | Suricata     | Network scan detected from attacker IP \
 T0+1 minute   | Sysmon       | PowerShell process execution           

The events occurred within a short time window (<5 minutes).

---

### Network Perspective

The Suricata alert indicates reconnaissance activity:

* Multiple ports scanned
* Source IP corresponds to attacker machine
* Target IP corresponds to monitored Windows host

This behavior aligns with early-stage attack activity.

---

### Endpoint Perspective

Sysmon logs confirm:

* Execution of "powershell.exe"
* Local process initiation on the same host targeted by the scan

---

## Correlation Logic

The detection hypothesis is based on the combination of:

```
IF:
- A network scan is detected
AND
- PowerShell execution occurs on the same host
WITHIN a short timeframe

THEN:
- The activity may indicate early-stage compromise or attacker interaction
```

---

## Threat Interpretation

This pattern may represent:

* Initial reconnaissance followed by execution
* Manual attacker interaction
* Preparation for lateral movement or exploitation

While not conclusive in a single case, the combination significantly increases suspicion compared to isolated events.

---

## 🧾 Conclusion

The analysis demonstrates that analyzing network and endpoint logs provides more robust detection and investigation capabilities than isolated analysis of logs from a single source.

This lab reflects the actual operation of a security operations center (SOC), where analysts must correlate multiple data sources to identify potential threats.
