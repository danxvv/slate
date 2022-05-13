---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> Para poder crear usuarios necesitas un Bearer Token y mandarlo en el header

<!-- ```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
``` -->

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


> Asegurate de reemplazar <YOUR_TOKEN> con el token que se te brindo.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>


# Leads

## Crear un Lead nuevo


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
    "phone":"123456789"
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
  "email": "juan@mail.com", "phone": "123456789"}, "tags": {"qb_fuente": 1, "qb_campaign": 1}}'
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
    "phone":"123456789"
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
Este Endpoint devuelve un código 201 cuando se crea un nuevo Lead.

### HTTP Request

`POST https://api.app.curadeuda.com/api/users`

### JSON Values User

Values | Type | Description
--------- | ------- | -----------
*`name` | string | Nombre del Lead
*`first_lastname` | string | Primer apellido del Lead
*`second_lastname` | string | Segundo apellido del Lead
*`email` | string | Correo electrónico del Lead
*`phone` | string | Teléfono del Lead

> Si la petición se hace correctamente, el servidor devolverá un código 200 y una respuesta en JSON.

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
### JSON Values Tags

Values | Type | Description
--------- | ------- | -----------
*`qb_fuente` | integer | ID de la fuente de Lead
*`qb_campaign` | integer | ID de la campaña de Lead
`cid` | string | CID si existe
`glid` | string | GLID si existe
`source` | string | Fuente de Lead
`campaign` | string | Campaña de Lead
`medium` | string | Medio de Lead
`adgroud` | string | Grupo de Adwords
`adgroup` | string | Grupo de Adwords
`matchtype` | string | Tipo de Match
`network` | string | Red de Lead
`device` | string | Dispositivo de Lead
`keyword` | string | Palabra clave de Lead
`placement` | string | Posición de Lead
`target` | string | Target de Lead
`adpositiion` | string | Posición de Adwords
`ip` | string | IP de Lead
`fbclid` | string | ID de Lead de Facebook
`param_1` | string | Parametro 1 de Lead
`param_2` | string | Parametro 2 de Lead
`param_3` | string | Parametro 3 de Lead
`param_4` | string | Parametro 4 de Lead
`param_5` | string | Parametro 5 de Lead

<aside class="success">
Recuerda que los campos con * son obligatorios.
</aside>



