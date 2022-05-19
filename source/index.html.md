---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: CuraDeuda API
---

# Introduction

Welcome to the CuraDeuda API documentation. Our goal is to provide a simple, easy to use API for vendors, who want to integrate their products with CuraDeuda.

This API allow you to create leads in CuraDeuda database.
# Authentication

> To create users you need a Bearer Token and send it in the headers.

```python
import requests

headers = {
  'Authorization': 'Bearer <YOUR_TOKEN>'
}

```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: Bearer <YOUR_TOKEN>"
```

```javascript
// With javascript, you can use the fetch API
const headers = {
  'Authorization': 'Bearer <YOUR_TOKEN>'
}
```


> Ensure that you replace <YOUR_TOKEN> with the token that was provided to you.

CuraDeuda API uses Bearer Tokens to allow vendors to use the API. Please contact us for a token.

`Authorization: Bearer YOUR_TOKEN`

<aside class="notice">
You must replace <code>YOUR_TOKEN</code> with your personal API key.
</aside>


# Leads

## Create a Lead

```python
import requests

headers = {
  'Authorization': 'Bearer <YOUR_TOKEN>'
}

lead = {
  "users":{
    "name":"Juan",
    "first_lastname":"Perez",
    "second_lastname":"Perez",
    "email":"juan@mail.com",
    "phone":"123456789",
    "rfc":"XXXX900101",
    "city":"Guadalajara",
    "suburb":"Centro",
    "street":"Street 1",
    "cp":"12345",
  },
  "tags":{
    "qb_fuente":1,
    "qb_campaign":1,

    }
}
response = requests.post('https://api.app.curadeuda.com/api/users,
  json=lead,
  headers=headers)
```

```shell
curl "https://api.app.curadeuda.com/api/users" \
  -H "Authorization: Bearer <YOUR_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{"users": {"name": "Juan", "first_lastname": "Perez", "second_lastname": "Perez", \
  "email": "juan@mail.com", "phone": "123456789", "rfc": "XXXX900101", "city": "Guadalajara", \
  "suburb": "Centro", "street": "Street 1", "cp": "12345" }, "tags": {"qb_fuente": 1, "qb_campaign": 1 }}'
```

```javascript
const headers = {
  'Authorization': 'Bearer <YOUR_TOKEN>'
}
let lead = {
  "users":{
    "name":"Juan",
    "first_lastname":"Perez",
    "second_lastname":"Perez",
    "email":"juan@mail.com",
    "phone":"123456789",
    "rfc":"XXXX900101",
    "city":"Guadalajara",
    "suburb":"Centro",
    "street":"Street 1",
    "cp":"12345"
  },
  "tags":{
    "qb_fuente":1,
    "qb_campaign":1,

    }
}
response = await fetch('https://api.app.curadeuda.com/api/users', {
  method: 'POST',
  headers: headers,
  body: JSON.stringify(lead)
})

```

> If the request is successful, the server will return a 201 status code and a JSON response.

```json
{
	"data": {
		"code": 201,
		"response": {
			"expedient": {
				"email": "juan@mail.com",
				"name": "Juan",
				"phone": "123456789"
			}
		}
	},
	"message": "user created successfully",
	"success": true
}
```

This endpoint returns a 201 code when a new lead is created.

### HTTP Request

`POST https://api.app.curadeuda.com/api/users`

### JSON Values User

Values | Type | Description
--------- | ------- | -----------
*`name` | string | Lead name
*`first_lastname` | string | Lead first lastname
*`second_lastname` | string | Lead Second lastname
*`email` | string | Lead email
*`phone` | string | Lead phone number
`rfc` | string | Lead RFC
`dateOfBirth` | string | Lead date of birth
`city` | string | Lead city
`street` | string | Lead street
`cp` | string | Lead postal code
`suburb` | string | Lead suburb

### JSON Values Tags

Values | Type | Description
--------- | ------- | -----------
*`qb_fuente` | integer | ID Source
*`qb_campaign` | integer | ID Campaign
`cid` | string | CID if exists
`glid` | string | GLID if exists
`source` | string | Source
`campaign` | string | Campaign
`medium` | string | Medium
`adgroud` | string | Adwords Group
`adgroup` | string | Adwords Group
`matchtype` | string | Matchtype
`network` | string | Network
`device` | string | Device
`keyword` | string | Keyword
`placement` | string | Placement
`target` | string | Target
`adpositiion` | string | Adwords Position
`ip` | string | IP
`fbclid` | string | Facebook Lead ID
`param_1` | string | Parameter for extra data
`param_2` | string | Parameter for extra data
`param_3` | string | Parameter for extra data
`param_4` | string | Parameter for extra data
`param_5` | string | Parameter for extra data

<aside class="success">
All values with * are required.
</aside>



