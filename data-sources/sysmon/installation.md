## Sysmon Installation

### Download
- Source: Microsoft Sysinternals

### Installation

Sysmon64.exe -accepteula -i sysmon-config.xml

### Configuration (basic)

```
<Sysmon>
  <EventFiltering>
    <ProcessCreate onmatch="include" />
    <NetworkConnect onmatch="include" />
  </EventFiltering>
</Sysmon>
```

### Integration with Wazuh

Edit:
C:\Program Files (x86)\ossec-agent\ossec.conf

Add:
```
<localfile>
  <location>Microsoft-Windows-Sysmon/Operational</location>
  <log_format>eventchannel</log_format>
</localfile>
```

Restart the Wazuh agent:
```
net stop wazuh
net start wazuh
```
