## Switches

#### Get switch detail
> Retrieve device detail by name and type

> Fields:
> * duplex: 0-Half, 1-Full
> * temperature: 0-normal, 1-hot, 2-very hot

* Method: GET
* URI: /api/v1/switches/{switch-id}
* Response Body:

```json
{
  "id": "4babe877-e098-9caf-74be-80e1c198644e",
  "type": "switch",
  "hostname": "Switch-A-SJ1",
  "mac": "00-14-22-01-23-45",
  "ip": "10.100.57.254",
  "sn": "JAL05300EJG",
  "temperature": 0,
  "up-since": 1530524843698,
  "vlans": [{
    "vlan-id": "1",
    "vlan-name": "vlan1"
  }],
  "interfaces": [{
    "index": 1,
    "status": "enabled/disabled",
    "link-status": "up/down",
    "port-speed": 100,
    "duplex": "Auto/Half/Full",
    "vlan": {
      "native-vlan": 1,
      "trunk-vlans": [2,3],
      "vlan-mode": "trunk"
    },
    "poe": "enabled/disabled",
    "desc": ""
  }],
  "interfaces-state": [{
      "index": 1,
      "status": "enabled/disabled",
      "link-status": "up/down",
      "speed": 100,
      "duplex": "Half/Full",
      "poe": {
          "link-state": "up",
          "class": 4,
          "max-power": 30000,
          "consumed-power": 20000
      }
    },
  ],
}
```

#### Apply Updated switch name to TSN

* Method: PUT
* URI: /api/v1/switches/{switch-id}/hostname
* Request Body:

```json
{
  "hostname": "new hostname"
}
```
* Response Code: 204
