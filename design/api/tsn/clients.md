## Clients

#### Get client summaries
> Get clients summary separated by wired and wireless
> How to distinct wired and wireless in network configuration ???

* Method: GET
* URI: /api/v1/clients/summary
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
