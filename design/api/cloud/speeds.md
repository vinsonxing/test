# Speed Service API

## Speed test

#### Get speed test results
> Get recent 100 speed test results

* Method: GET
* URI: /api/v1/sites/{site-id}/speeds
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

## Save Speed test result
> Once speed test is completed, save the test result to cloud

* Method: POST
* URI: /api/v1/sites/{site-id}/speeds
* Request Body:

```json
{
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
}
```

* Response Body:

```json
{
  "id": "9801ce5f-910b-49ad-ab95-cb1befc7174c"
}
```
