## Switches

#### Get switch detail
> Retrieve device detail by name and type

> Fields:
> * duplex: 0-Half, 1-Full
> * temperature: 0-normal, 1-hot, 2-very hot

* Method: GET
* URI: /api/v1/sites/{site-id}/switches/{switch-id}
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
  "networks": [{
      "id": "5b444ea7-26ce-ee12-1381-31219f69ad9c",
      "name": "Employee Network 1",
    },{
      "id": "93a55c8f-f463-fa9b-0601-255e08364a36",
      "name": "Guest Network 1",
    },
  ],
  "ports": [{
    "index": 1,
    "administrative": {
      "status": "enabled/disabled",
      "link-status": "up/down",
      "port-speed": 100,
      "duplex": 1,
      "vlans": [{
        "vlan-id": "1",
        "vlan-name": "vlan1"
      }]
    },
    "operational": {
      "status": "enabled/disabled",
      "link-status": "up/down",
      "speed": 100,
      "duplex": 1,
      "vlans": [{
        "vlan-id": "1",
        "vlan-name": "vlan1"
      }]
    },
    "poe": "enabled/disabled",
    "desc": ""
  }]
}
```

#### Create switch
* Method: POST
* URI: /api/v1/sites/{site-id}/switches
* Request Body:


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
{
  "id": "4babe877-e098-9caf-74be-80e1c198644e",
  "type": "switch",
  "hostname": "Switch-A-SJ1",
  "mac": "00-14-22-01-23-45",
  "ip": "10.100.57.254",
  "sn": "JAL05300EJG",
  "temperature": 0,
  "up-since": 1530524843698,
  "networks": [{
      "id": "5b444ea7-26ce-ee12-1381-31219f69ad9c",
      "name": "Employee Network 1",
    },{
      "id": "93a55c8f-f463-fa9b-0601-255e08364a36",
      "name": "Guest Network 1",
    },
  ],
  "ports": [{
    "index": 1,
    "administrative": {
      "status": "enabled/disabled",
      "link-status": "up/down",
      "port-speed": 100,
      "duplex": 1,
      "vlans": [{
        "vlan-id": "1",
        "vlan-name": "vlan1"
      }]
    },
    "operational": {
      "status": "enabled/disabled",
      "link-status": "up/down",
      "speed": 100,
      "duplex": 1,
      "vlans": [{
        "vlan-id": "1",
        "vlan-name": "vlan1"
      }]
    },
    "poe": "enabled/disabled",
    "desc": ""
  }]
}
```

#### Update switch name

* Method: PUT
* URI: /api/v1/sites/{site-id}/switches/{switch-id}/hostname
* Request Body:

```json
{
  "hostname": "new hostname"
}
```
* Response Code: 204
