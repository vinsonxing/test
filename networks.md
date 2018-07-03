## Networks

#### Get Network detail
> Get network detail settings

> Fields:
* security: 0-Low, 1-Medium, 2-High
* wifi-auth: for PSK and radius, additional inputs are needed which will be saved to field wifi-auth-values. such as for PSK, there should be one value for the PSK value. for radius, there should be values for radius server address and port


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
  "security": 1,
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10
}
```

#### Save Network

* Method: PUT
* URI: /api/networks/{network-id}
* Response Body:

```json
{
  "name": "Employee Network 1",
  "wifi-status-enable": true,
  "wifi-auth": "open/psk/radius",
  "wifi-auth-values": [""],
  "wired-auth": "enabled/disabled",
  "security": 2,
  "multicast": "enabled/disabled",
  "number-of-users": 150,
  "rate-limit": 10
}
```
* Response Code: 204


#### Delete Network detail

* Method: DELETE
* URI: /api/networks/{network-id}
* Response Code: 204
