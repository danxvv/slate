# Errors

> response for 400 status code

```json
{
  "success": false,
  "message": "Usuario existente en nuestra base de datos"
}
```

> response for 401 status code if bearer is not provided

```json
{
	"msg": "Invalid Header"
}
```

> response for 401 status code if bearer is invalid

```json
{
  "msg": "Invalid Token"
}
```

> response for 500 status code

```json
{
    "success": false,
    "message": "Internal Server Error -- Tenemos un problema, comunicate con nosotros."
}
```

The following errors are returned by the API:


Error Code | Meaning
---------- | -------
400 | Lead already exists
401 | Unauthorized -- Invalid bearer token or no bearer token provided
500 | Internal Server Error -- We have a problem, please contact us.
