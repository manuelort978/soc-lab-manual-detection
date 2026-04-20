## Suspicious behavior
{
  "_index": "wazuh-alerts-4.x-2026.04.19",
  "_id": "hZZfpp0BlXsNtIXDK5lE",
  "_score": null,
  "_source": {
    "input": {
      "type": "log"
    },
    "agent": {
      "ip": "192.168.56.105",
      "name": "w10.agent.skynet",
      "id": "001"
    },
    "manager": {
      "name": "ubuntu-server"
    },
    "data": {
      "ip_v": "4",
      "in_iface": "\\Device\\NPF_{90BB902E-B997-4D62-ACD4-8D0BC153F65F}",
      "src_ip": "192.168.56.103",
      "src_port": "53140",
      "event_type": "alert",
      "alert": {
        "severity": "2",
        "signature_id": "2010937",
        "rev": "3",
        "metadata": {
          "updated_at": [
            "2019_07_26"
          ],
          "confidence": [
            "Medium"
          ],
          "created_at": [
            "2010_07_30"
          ],
          "signature_severity": [
            "Informational"
          ]
        },
        "gid": "1",
        "signature": "ET SCAN Suspicious inbound to mySQL port 3306",
        "action": "allowed",
        "category": "Potentially Bad Traffic"
      },
      "flow_id": "2179556770808404.000000",
      "dest_ip": "192.168.56.105",
      "proto": "TCP",
      "dest_port": "3306",
      "pkt_src": "wire/pcap",
      "flow": {
        **"src_ip": "192.168.56.103"**,
        "src_port": "53140",
        "pkts_toserver": "1",
        **"dest_ip": "192.168.56.105"**,
        "start": "2026-04-19T09:32:23.048715-0900",
        "bytes_toclient": "0",
        "bytes_toserver": "60",
        "pkts_toclient": "0",
        "dest_port": "3306"
      },
      "timestamp": "2026-04-19T09:32:23.048715-0900",
      "direction": "to_server"
    },
    "rule": {
      "firedtimes": 1,
      "mail": false,
      "level": 3,
      **"description": "Suricata: Alert - ET SCAN Suspicious inbound to mySQL port 3306"**,
      "groups": [
        "ids",
        "suricata"
      ],
      **"id": "86601"**
    },
    "location": "C:\\Program Files\\Suricata\\log\\eve.json",
    "decoder": {
      "name": "json"
    },
    "id": "1776612743.1731773",
    "timestamp": "2026-04-19T09:32:23.504-0600"
  },
  "fields": {
    "timestamp": [
      "2026-04-19T15:32:23.504Z"
    ],
    "data.timestamp": [
      "2026-04-19T18:32:23.048Z"
    ]
  },
  "sort": [
    1776612743504
  ]
}


## Port analyzis from suspicious IP

{
  "_index": "wazuh-alerts-4.x-2026.04.19",
  "_id": "hpZfpp0BlXsNtIXDK5lE",
  "_score": null,
  "_source": {
    "input": {
      "type": "log"
    },
    "agent": {
      "ip": "192.168.56.105",
      "name": "w10.agent.skynet",
      "id": "001"
    },
    "manager": {
      "name": "ubuntu-server"
    },
    "data": {
      "ip_v": "4",
      "in_iface": "\\Device\\NPF_{90BB902E-B997-4D62-ACD4-8D0BC153F65F}",
      "src_ip": "192.168.56.103",
      "src_port": "53139",
      "event_type": "alert",
      "alert": {
        "severity": "2",
        "signature_id": "2010937",
        "rev": "3",
        "metadata": {
          "updated_at": [
            "2019_07_26"
          ],
          "confidence": [
            "Medium"
          ],
          "created_at": [
            "2010_07_30"
          ],
          "signature_severity": [
            "Informational"
          ]
        },
        "gid": "1",
        **"signature": "ET SCAN Suspicious inbound to mySQL port 3306"**,
        "action": "allowed",
        "category": "Potentially Bad Traffic"
      },
      "flow_id": "1818739432158091.000000",
      "dest_ip": "192.168.56.105",
      "proto": "TCP",
      "dest_port": "3306",
      "pkt_src": "wire/pcap",
      "flow": {
        **"src_ip": "192.168.56.103"**,
        "src_port": "53139",
        "pkts_toserver": "1",
        **"dest_ip": "192.168.56.105"**,
        "start": "2026-04-19T09:32:22.947746-0900",
        "bytes_toclient": "0",
        "bytes_toserver": "60",
        "pkts_toclient": "0",
        "dest_port": "3306"
      },
      "timestamp": "2026-04-19T09:32:22.947746-0900",
      "direction": "to_server"
    },
    "rule": {
      "firedtimes": 2,
      "mail": false,
      "level": 3,
      "description": "Suricata: Alert - ET SCAN Suspicious inbound to mySQL port 3306",
      "groups": [
        "ids",
        "suricata"
      ],
     **"id": "86601"**
    },
    "location": "C:\\Program Files\\Suricata\\log\\eve.json",
    "decoder": {
      "name": "json"
    },
    "id": "1776612743.1733734",
    "timestamp": "2026-04-19T09:32:23.504-0600"
  },
  "fields": {
    "timestamp": [
      "2026-04-19T15:32:23.504Z"
    ],
    "data.timestamp": [
      "2026-04-19T18:32:22.947Z"
    ]
  },
  "sort": [
    1776612743504
  ]
}
