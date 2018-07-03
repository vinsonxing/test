# Dashboard Service APIs

## Speed test

#### Get speed
> Get upload and download average speed in last **duration** seconds, default value is 300 (5 minutes)

* Method: GET
* URI: /api/dashboard/speed
  - parameters: duration
* Response Body:

```json
 {
   "upload": {
     "max": 20,
     "current": 0.17
   },
   "download": {
     "max": 100,
     "current": 54.17
   }
 }
```
Response Code: 200 (404 if not found)

> Hints: speed unit is Mb per second: Mb/s

#### Get speed test results
> Get recent 100 speed test results

* Method: GET
* URI: /api/dashboard/speed-test/results
* Response Body:

```json
[{
  "id": "9801ce5f-910b-49ad-ab95-cb1befc7174c",
  "status": "completed/running",
  "tester": {
    "username": "john",
    "display-name": "John Smith"
  },
  "results": {
    "upload": 20,
    "download": 100
  },
  "time": 1530512597135
},
]
```
* Response Code: 200 (404 if not found)

#### Launch speed test
> Launch speed test, this test is for the case TSN to cloud. TSN should handle this test and provide API to retrieve the current test result.

* Method: POST
* URI: /api/dashboard/speed-test
* Request Body: N/A
* Response body:

```json
{
  "id": "9801ce5f-910b-49ad-ab95-cb1befc7174c"
}
```
* Response Code: 201

### Get a specific speed test result
> Get a specific speed test result. If the status of target speed test is running, show a progress bar on GUI until the target status is "completed".

> Fields:
> - status: status of current speed test, options: "running/completed"
> - results->upload: upload speed of the current test
> - results->download: download speed of the current test

* Method: GET
* URI: /api/dashboard/speed-test/results/{id}
* Response Body:

```json
{
  "id": "9801ce5f-910b-49ad-ab95-cb1befc7174c",
  "status": "running/completed",
  "tester": {
    "username": "john",
    "display-name": "John Smith"
  },
  "results": {
    "upload": 20,
    "download": 100
  },
  "time": 1530512597135
}
```
* Response Code: 200 (404 if not found)

## Security

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
* URI: /api/dashboard/securities
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


#### Save security item
> Save a specific security configuration item

* Method: PUT
* URI: /api/dashboard/securities/{name}
* Request Body:

```json
{
  "name": "firewall",
  "value": "High"
}
```
* Response Code: 204


## Attentions

#### Get attentions
> Retrieve all attentions

> Support pagination

> The values of name, message and action are all predefined, and support i18n.

> Fields:
> - action: should be mapped with corresponding GUI page for next action. According the value of this field, GUI will render a corresponding link to process this action.
> - message-data: values for the placeholders for field "message"

* Method: GET
* URI: /api/dashboard/attentions
* Query Parameters:
  - page, size, sort (by field type), default value: size=10
* Response Body:

```json
{  
  "page": 0,
  "size": 10,
  "total": 25,
  "data": [{
    "type": "resolve_unclaimed_device",
    "message": "message_key",
    "message-data": [],
    "timestamp": 1530512597135,
    "action": "action_type"
  },
 ]
}
```

## Networks

#### Get networks
> Get all configured network list

* Method: GET
* URI: /api/dashboard/networks
* Response Body:

```json
[{
  "id": "en1",
  "name": "Employee Network 1",
  "capacity": 250,
  "allocated": 187
  }, {
    "id": "gn1",
    "name": "Guest Network 1",
    "capacity": 125,
    "allocated": 72
  },
]
```

## Devices

#### Get all devices summary
> Get devices info

> If error exists, an indicator will be shown, and detail info will be shown once the indicator is pressed.

> If multiple errors exist, show an error list.

> Fields:
> * status: 0-offline, 1-online


* Method: GET
* URI: /api/dashboard/devices
* Response Body:

```json
[{
    "type": "router",
    "devices": [{
        "hostname": "router1",
        "status": 1,
        "messages": [{
            "message": "message_key",
            "message-data": [],
            "timestamp": 1530512597135,
          }
        ]
    }]
},{
    "type": "switch",
    "devices": [{
        "hostname": "switch1",
        "status": 1,
        "messages": [{
            "message": "message_key",
            "message-data": [],
            "timestamp": 1530512597135,
          }
        ]
    }]
},{
    "type": "access-point",
    "devices": [{
        "hostname": "ap1",
        "status": 1,
        "messages": [{
            "message": "message_key",
            "message-data": [],
            "timestamp": 1530512597135,
          }
        ]
    },{
        "hostname": "ap2",
        "status": 0,
        "messages": [{
            "message": "message_key",
            "message-data": [],
            "timestamp": 1530512597135,
          }
        ]
    }]
}]
```


## Clients

#### Get clients summary
> Get clients summary separated by wired and wireless

* Method: GET
* URI: /api/dashboard/clients
* Response Body:

```json
{
  "wired": {
    "capacity": 1000,
    "connected": 687
  },
  "wireless": {
    "capacity": 400,
    "connected": 123
  }
}
```
