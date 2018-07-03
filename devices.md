## Switches

#### Get switch detail
> Retrieve device detail by name and type

> Fields:
> * duplex: 0-Half, 1-Full

* Method: GET
* URI: /api/devices/switch/{hostname}
* Response Body:

```json
{
  "type": "switch",
  "hostname": "Switch-A-SJ1",
  "mac": "00-14-22-01-23-45",
  "ip": "10.100.57.254",
  "sn": "JAL05300EJG",
  "temperature": 78.98,
  "temperature-unit": "F/C",
  "up-since": 1530524843698,
  "networks": [{
      "name": "Employee Network 1",
      "allocated": 100
    },{
        "name": "Guest Network 1",
        "allocated": 20
    },
  ],
  "ports": [{
    "index": 1,
    "administrative": {
      "status": "enabled/disabled",
      "link-status": "up/down",
      "port-speed": 100,
      "duplex": 1,
      "vlans": [""]
    },
    "operational": {
      "status": "enabled/disabled",
      "link-status": "up/down",
      "speed": 100,
      "duplex": 1,
      "vlans": [""]
    },
    "poe": "enabled/disabled",
    "desc": ""
  }]
}
```

#### Update switch name

* Method: PUT
* URI: /api/devices/switch/{hostname}
* Request Body:

```json
{
  "hostname": "new hostname"
}
```
* Response Code: 204
