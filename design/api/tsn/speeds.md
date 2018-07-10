# Internet speed Service APIs

## Speed test

#### Get speed
> Get upload and download average speed in last **duration** seconds, default value is 300 (5 minutes)

* Method: GET
* URI: /api/v1/speed
  - parameters: duration
* Response Body:

```json
 {
   "upload": 0.17,
   "download": 54.17
 }
```
Response Code: 200 (404 if not found)

> Hints: speed unit is Mb per second: Mb/s

#### Launch speed test
> Launch speed test, this test is for the case TSN to cloud. TSN should handle this test and provide API to retrieve the current test result.

> If there is one running speed test, return error message

* Method: POST
* URI: /api/v1/speed
* Request Body:

```json
{
  "tester": {
    "username": "john",
    "display-name": "John Smith"
  }
}
```
>> Hints: **tester** will be populated to speed test result
* Response body: N/A
* Response Code: 201

### Get a current running speed test result
> Get the last running speed test result. If the status of target speed test is running, show a progress bar on GUI until the target status is "completed".

> Fields:
> - status: status of current speed test, options: "running/completed"
> - results->upload: upload speed of the current test
> - results->download: download speed of the current test

* Method: GET
* URI: /api/v1/speed/result
* Response Body:

```json
{
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
