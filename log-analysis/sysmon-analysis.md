## Windows PowerShell process creation ##
{
  "_index": "wazuh-alerts-4.x-2026.04.19",
  "_id": "yJZgpp0BlXsNtIXD5ZkA",
  "_score": null,
  "_source": {
    "input": {
      "type": "log"
    },
    "agent": {
      **"ip": "192.168.56.105"**,
      "name": "w10.agent.skynet",
      "id": "001"
    },
    "manager": {
      "name": "ubuntu-server"
    },
    "data": {
      "win": {
        "eventdata": {
          "subjectLogonId": "0x3e7",
          "parentProcessName": "C:\\\\Windows\\\\System32\\\\CompatTelRunner.exe",
          "subjectDomainName": "WORKGROUP",
          "tokenElevationType": "%%1936",
          "newProcessId": "0x2350",
          "mandatoryLabel": "S-1-16-16384",
          **"newProcessName": "C:\\\\Windows\\\\System32\\\\WindowsPowerShell\\\\v1.0\\\\powershell.exe"**,
          "targetLogonId": "0x0",
          "subjectUserSid": "S-1-5-18",
          "processId": "0x1fa8",
          **"commandLine": "powershell.exe -ExecutionPolicy Restricted -Command Write-Host 'Final result: 1';"**,
          "targetUserSid": "S-1-0-0",
          "subjectUserName": "DESKTOP-FAB7C03$"
        },
        "system": {
          **"eventID": "4688"**,
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          **"message": "\"A new process has been created.\r\n\r\nCreator Subject:\r\n\tSecurity ID:\t\tS-1-5-18\r\n\tAccount Name:\t\tDESKTOP-FAB7C03$\r\n\tAccount Domain:\t\tWORKGROUP\r\n\tLogon ID:\t\t0x3E7\r\n\r\nTarget Subject:\r\n\tSecurity ID:\t\tS-1-0-0\r\n\tAccount Name:\t\t-\r\n\tAccount Domain:\t\t-\r\n\tLogon ID:\t\t0x0\r\n\r\nProcess Information:\r\n\tNew Process ID:\t\t0x2350\r\n\tNew Process Name:\tC:\\Windows\\System32\\WindowsPowerShell\\v1.0\\powershell.exe\r\n\tToken Elevation Type:\t%%1936\r\n\tMandatory Label:\t\tS-1-16-16384\r\n\tCreator Process ID:\t0x1fa8\r\n\tCreator Process Name:\tC:\\Windows\\System32\\CompatTelRunner.exe\r\n\tProcess Command Line:\tpowershell.exe -ExecutionPolicy Restricted -Command Write-Host 'Final result: 1';\r\n\r\nToken Elevation Type indicates the type of token that was assigned to the new process in accordance with User Account Control policy.\r\n\r\nType 1 is a full token with no privileges removed or groups disabled.  A full token is only used if User Account Control is disabled or if the user is the built-in Administrator account or a service account.\r\n\r\nType 2 is an elevated token with no privileges removed or groups disabled.  An elevated token is used when User Account Control is enabled and the user chooses to start the program using Run as administrator.  An elevated token is also used when an application is configured to always require administrative privilege or to always require maximum privilege, and the user is a member of the Administrators group.\r\n\r\nType 3 is a limited token with administrative privileges removed and administrative groups disabled.  The limited token is used when User Account Control is enabled, the application does not require administrative privilege, and the user does not choose to start the program using Run as administrator.\""**,
          "version": "2",
          "systemTime": "2026-04-19T16:33:44.0445009Z",
          "eventRecordID": "49494",
          "threadID": "292",
          "computer": "DESKTOP-FAB7C03",
          "task": "13312",
          "processID": "4",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "firedtimes": 334,
      "mail": false,
      "level": 3,
      "description": "A process was created.",
      "groups": [
        "windows",
        " WEF"
      ],
      "id": "67027"
    },
    "location": "EventChannel",
    "decoder": {
      "name": "windows_eventchannel"
    },
    "id": "1776612854.2087815",
    "timestamp": "2026-04-19T09:34:14.235-0600"
  },
  "fields": {
    "timestamp": [
      "2026-04-19T15:34:14.235Z"
    ]
  },
  "sort": [
    1776612854235
  ]
}
