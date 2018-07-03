## Networks

#### Get Network detail
> Get network detail settings

> Fields:
* security: 0-Low, 1-Medium, 2-High
* wifi-auth: for psk and radius, additional inputs are needed and will be save to wifi-auth-values. such as for psk, there should be one value for the psk value. for radius, there should be values for radius server addresss and port

* Method: GET
* URI: /api/networks/{network-id}
* Response Body:

```json
{
  "id": "en1",
  "name": "Employee Network 1",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wifi-auth-values": [""],
  "wired-auth": "enabled/disabled",
  "security": "High/Medium/Low",
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10
}
```

#### Save Network detail

* Method: PUT
* URI: /api/networks/{network-id}
* Response Body:

```json
{
  "id": "en1",
  "name": "Employee Network 1",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wired-auth-enable": true,
  "security": "High/Medium/Low",
  "multicast-enable": true,
  "number-of-users": 150,
  "rate-limit": 10
}
```
* Response Code: 204


#### Delete Network detail

* Method: DELETE
* URI: /api/networks/{network-id}
* Response Code: 204
