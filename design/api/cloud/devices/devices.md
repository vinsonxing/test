## Devices

#### Get device summaries
> Get devices info

* Method: GET
* URI: /api/v1/sites/{site-id}/devices/summary
* Response Body:

```json
[{
    "type": "router",
    "devices": [{
        "id": "14ba6fe8-62cb-5bbc-f577-ecab8bea86e7",
        "hostname": "router1"
    }]
},{
    "type": "switch",
    "devices": [{
        "id": "0f6d7d02-f2a7-7ede-ea67-482bf0a6299e",
        "hostname": "switch1"
    }]
},{
    "type": "access-point",
    "devices": [{
        "id": "2c455a2a-1eec-5171-5843-924c26808984",
        "hostname": "ap1"
    },{
        "id": "",
        "hostname": "ap2"
    }]
}]
```
