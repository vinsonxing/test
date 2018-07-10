# Security

#### Apply security item to TSN
> Apply specific security configuration item to TSN.
> TSN will handle the detail security settings according to security value.

* Method: PATCH
* URI: /api/v1/securities/{name}
* Request Body:

```json
{
  "name": "firewall",
  "value": "High"
}
```
* Response Code: 204
