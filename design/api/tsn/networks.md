## Networks

#### Create new Network
> Create new network and apply all the configuration items to TSN
> TODO add allocated info
* Method: POST
* URI: /api/v1/networks
* Request Body:

```json
{
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
* Response Body:

```json
{
  "id": "5b444ea7-26ce-ee12-1381-31219f69ad9c"
}
```
* Response Code: 201

#### Apply network configuration to TSN

* Method: PUT
* URI: /api/v1/networks/{network-id}
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
  "subnet": "192.168.0.0/24"
}
```
* Response Body: N/A
* Response Code: 204


#### Delete network

* Method: DELETE
* URI: /api/v1/networks/{network-id}
* Response Code: 204


#### Get Network allocated count

* Method: GET
* URI: /api/v1/networks/{network-id}/allocated
* Query Parameter:
- switch: switch=switch-id
> Get clients by switch, if not provided, return all clients
in network: {network-id}

* Response Body:

```json
[
  {
    "id": "4babe877-e098-9caf-74be-80e1c198644e",
    "hostname": "switch1",
    "allocated": 117
  },
  {
    "id": "d8560b76-70df-fc30-7740-dba60f6b6e08",
    "hostname": "switch2",
    "allocated": 200
  }
]
```
