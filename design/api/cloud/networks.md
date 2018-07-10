## Networks

#### Get Network list
> Get all configured network list

* Method: GET
* URI: /api/v1/sites/{site-id}/networks
* Response Body:

```json
[{
  "id": "5b444ea7-26ce-ee12-1381-31219f69ad9c",
  "name": "Employee Network 1",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wifi-auth-values": [""],
  "wired-auth": "enabled/disabled",
  "security": 2,
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10,
  "guest": false,
  "subnet": "192.168.1.0/24",
  "vlan": 11
  }, {
    "id": "93a55c8f-f463-fa9b-0601-255e08364a36",
    "name": "Guest Network 1",
    "wifi-status-enable": true,
    "wifi-auth": "open/psk/radius",
    "wifi-auth-values": [""],
    "wired-auth": "enabled/disabled",
    "security": 2,
    "multicast": "enabled/disabled",
    "number-of-users": 150,
    "rate-limit": 10,
    "guest": true,
    "subnet": "192.168.0.0/24",
    "vlan": 11
  },
]
```

#### Get a specific network

* Method: GET
* URI: /api/v1/sites/{site-id}/networks/{network-id}
* Response Body:

```json
{
  "id": "5b444ea7-26ce-ee12-1381-31219f69ad9c",
  "name": "Employee Network 1",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wifi-auth-values": [""],
  "wired-auth": "enabled/disabled",
  "security": 2,
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10,
  "guest": false,
  "subnet": "192.168.1.0/24",
  "vlan": 11
}
```

#### Create new Network

* Method: POST
* URI: /api/v1/sites/{site-id}/networks
* Request Body:

```json
{
  "id": "5b444ea7-26ce-ee12-1381-31219f69ad9c",
  "name": "Employee Network New",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wifi-auth-values": [""],
  "wired-auth": "enabled/disabled",
  "security": 2,
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10,
  "guest": true,
  "subnet": "192.168.0.0/24",
  "vlan": 11
}
```
* Response Body: N/A
* Response Code: 201

#### Save new Network

* Method: PUT
* URI: /api/v1/sites/{site-id}/networks/{network-id}
* Request Body:

```json
{
  "name": "Employee Network Update",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wifi-auth-values": [""],
  "wired-auth": "enabled/disabled",
  "security": 2,
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10,
  "guest": true,
  "subnet": "192.168.0.0/24",
  "vlan": 11
}
```
* Response Body: N/A
* Response Code: 204

#### Delete network

* Method: DELETE
* URI:  /api/v1/sites/{site-id}/networks/{network-id}
* Response Code: 204
