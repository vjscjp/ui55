# Marathon Utility
Basic utility rest api in Go using marathon endpoints.

## Getting Started
1. Simple clone the repo or download the repo.
2. Then go to you working directory and run the main.go by command - run main.go
3. You will get end point url, App will be running on port no - 8888 So you can use any rest client and test below API or To validate API you can simply go to your browser and hit "http://localhost:8888".


## Endpoints
- **Default API - GET /
```
### Request
    No Request
    
### Response
{
    "Status": "OK"
}

```

- **Login API - POST /login
```
### Request
{
	"id": {marathon username},
	"pass": {marathon password},
	"api": {marathon endpoint}
}
### Response
{
	"StatusCode": 200,
	"Status": "OK",
	"Apps": [{
		"id": "/mantl-api",
		"text": "/mantl-api"
	}, {
		"id": "/test--efb79a-19529-0",
		"text": "/test--efb79a-19529-0"
	}],
    "Token": "XXXXXXXXXXXXXXXXXXXXXXXX="
}
```

- **List Of Apps API - GET /apps
```
### Request Header
X-Token : {token generated at the time of login}

### Response
[{
	"id": "/mantl-api",
	"text": "/mantl-api"
}, {
	"id": "/test--efb79a-19529-0",
	"text": "/test--efb79a-19529-0"
}]

```

- **Get App By Id API - GET /apps/{id}
```
### Request Header
X-Token : {token generated at the time of login}
### Response
{
	"id": "/david-staging--traefik-kafka-3--traefik-kafka-cmx-3--807e8c",
	"projectname": "traefik-kafka-3",
	"projectid": "19c60964-0621-11e6-bd9b-0242ac110003",
	"envname": "david-staging",
	"envid": "70fe6d48-0622-11e6-bdad-0242ac110003",
	"servicename": "traefik-kafka-cmx-3",
	"serviceid": "3ab53f68-0621-11e6-bd9f-0242ac110003",
	"tasks": [{
		"host": "shipped-tx3-infra-204.node.consul",
		"ports": [31040],
		"id": "david-staging--traefik-kafka-3--traefik-kafka-cmx-3--807e8c.80b63a12-1356-11e6-a6d7-6296a94e7041",
		"appid": "/david-staging--traefik-kafka-3--traefik-kafka-cmx-3--807e8c"
	}]
}
```

- **Get App By Hostname and Port No API - GET /hostport/{hostname}/{portno}
```
### Request Header
X-Token : {token generated at the time of login}
### Response
{
	"id": "/david-staging--traefik-kafka-3--traefik-kafka-cmx-3--807e8c",
	"projectname": "traefik-kafka-3",
	"projectid": "19c60964-0621-11e6-bd9b-0242ac110003",
	"envname": "david-staging",
	"envid": "70fe6d48-0622-11e6-bdad-0242ac110003",
	"servicename": "traefik-kafka-cmx-3",
	"serviceid": "3ab53f68-0621-11e6-bd9f-0242ac110003",
	"tasks": [{
		"host": "shipped-tx3-infra-204.node.consul",
		"ports": [31040],
		"id": "david-staging--traefik-kafka-3--traefik-kafka-cmx-3--807e8c.80b63a12-1356-11e6-a6d7-6296a94e7041",
		"appid": "/david-staging--traefik-kafka-3--traefik-kafka-cmx-3--807e8c"
	}]
}
```

- **Logout Application API - GET /logout
```
### Request Header
X-Token : {token generated at the time of login}
### Response
{
	"StatusCode": 200,
	"Status": "Successfully Logged Out",
	"Apps": null,
	"Token": ""
}
```


## Requirements
* [Marathon End Point](https://mesosphere.github.io/marathon/docs/rest-api.html)

## Credits
- [Vijay P.](https://github.com/vjscjp)
