## Suricata Installation (Windows)

### Requirements
- Notepad++
- Npcap
- Suricata
- Emerging Threats rules

---

### Configuration

Edit:
C:\Program Files\Suricata\suricata.yaml

Set:
```
address-groups:
  HOME_NET: "[IP_WINDOWS]"

rule-files:
  - emerging-all.rules
```
*To avoid errors, we need to comment the entire block of rules, leaving only "emerging-all.rules"

---

### Get Interface UUID with CMD
```
Get-CimInstance Win32_NetworkAdapterConfiguration |
Where-Object { $_.IPAddress } |
Select-Object @{n="IPAddress";e={$_.IPAddress -join ", "}}, SettingID
```
---

### Run Suricata in CMD with administrator privileges
```
"C:\Program Files\Suricata\suricata.exe" -c "C:\Program Files\Suricata\suricata.yaml" -i \Device\NPF_{UUID}
```
---

### To check Log File 

C:\Program Files\Suricata\log\eve.json

---

### Wazuh Integration

Edit:
C:\Program Files (x86)\ossec-agent\ossec.conf

Add:
```
<localfile>
  <log_format>json</log_format>
  <location>C:\Program Files\Suricata\log\eve.json</location>
</localfile>
```

Restart agent:
```
net stop wazuh
net start wazuh
```
