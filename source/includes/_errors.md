# Errors

> respuesta de codigo 400

```json
{
  "success": false,
  "message": "Usuario existente en nuestra base de datos"
}
```

> respuesta de codigo 401

```json
{
  "success": false,
  "message": "Unauthorized -- Tu API es invalida."
}
```

> respuesta de codigo 500

```json
{
    "success": false,
    "message": "Internal Server Error -- Tenemos un problema, comunicate con nosotros."
}
```
<aside class="notice">
This error section is stored in a separate file in <code>includes/_errors.md</code>. Slate allows you to optionally separate out your docs into many files...just save them to the <code>includes</code> folder and add them to the top of your <code>index.md</code>'s frontmatter. Files are included in the order listed.
</aside>

El API podria responder algunos de estos codigos de error:


Error Code | Meaning
---------- | -------
400 | Usuario existente en nuestra base de datos
401 | Unauthorized -- Tu API es invalida.
500 | Internal Server Error -- Tenemos un problema, comunicate con nosotros.
