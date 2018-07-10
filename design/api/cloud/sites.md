## Sites

#### Get All Sites
> Retrieve all sites,

> Leverage this api to show site list, once user selected one site, record this site id
> and append this site id to HTTP request header when accessing APIs for the specific site.

* Method: GET
* URI: /api/v1/sites
* Response Body:

```json
[{
  "id": "f294bf31-8bf1-4ec2-98f2-c87666932281",
  "name": "Site 1",
  "location": {
    "address": "",
    "country": "",
    "state": "",
    "zip-code": "",
    "latitude": "",
    "longitude": ""
  },
  "description": ""
},
]
```

#### Get a specific site

* Method: GET
* URI: /api/v1/sites/{site-id}
* Response Body:

```json
{
  "id": "f294bf31-8bf1-4ec2-98f2-c87666932281",
  "name": "Site 1",
  "location": {
    "address": "",
    "country": "",
    "state": "",
    "zip-code": "",
    "latitude": "",
    "longitude": ""
  },
  "description": ""
}
```

#### Create a site

* Method: POST
* URI: /api/v1/sites
* Request Body:

```json
{
  "name": "Site 1",
  "location": {
    "address": "",
    "country": "",
    "state": "",
    "zip-code": "",
    "latitude": "",
    "longitude": ""
  },
  "description": ""
}
```

* Response Body:

```json
{
  "id": "f294bf31-8bf1-4ec2-98f2-c87666932281"
}
```

* Response Code: 201

#### Update a site

* Method: PUT
* URI: /api/v1/sites/{site-id}
* Reqeust Body:

```json
{
  "name": "Site 1",
  "location": {
    "address": "",
    "country": "",
    "state": "",
    "zip-code": "",
    "latitude": "",
    "longitude": ""
  },
  "description": ""
}
```
* Response Code: 204

#### Delete a site
* Method: DELETE
* URI: /api/v1/sites/{site-id}
* Response Code: 204
