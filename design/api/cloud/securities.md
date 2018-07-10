# Security

#### Get security configuration items
> Get all security configuration items with configured values.

> Return an array of configurations.

> Fields:
> - name: [string] configuration item key, support i18n
> - value: [string] configuration value
> - type: [string] configuration type, which is used for presentation style. Security item should be rendered according to the type.
> - desc-data: variables should be shown in "desc"
> - desc: virtual field for i18n support, which is the message shown under item name, here it is a message key, which will be translated in different languages, its value format can be something like **dashboard_security_desc_[name]**. Such as "3 Clients" in mockup against VPN configuration , the message key should be dashboard_security_desc_**vpn**, and there should be an default English string against this key: "{0} Clients" in English language file, "{0}" is a placeholder, the value of it is from field "desc-data".


* Method: GET
* URI: /api/v1/sites/{site-id}/securities/summary
* Response Body:

```json
[
  {
    "name": "firewall",
    "value": "Medium",
    "desc-data": [],
    "type": "string"
  },{
    "name": "umbrella",
    "value": "false",
    "desc-data": [],
    "type": "boolean"
  },{
    "name": "vpn",
    "value": "true",
    "desc-data": ["3"],
    "type": "boolean"
  },{
    "name": "ipsec",
    "value": "false",
    "desc-data": [],
    "type": "boolean"
  },{
    "name": "intvalue",
    "value": "100",
    "desc-data": [],
    "type": "int"
  }
]
```
* Response Code: 200 (404 if not found)


#### Save security item to cloud
> Save a specific security configuration item to cloud

* Method: PATCH
* URI: /api/v1/sites/{site-id}/securities/{name}
* Request Body:

```json
{
  "name": "firewall",
  "value": "High"
}
```
* Response Code: 204
