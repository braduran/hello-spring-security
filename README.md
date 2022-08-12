### Descripción
Este proyecto consiste en una autenticación que genera un token jwt, para enviar dicho token en las peticiones posteriores.
Para lograr esto se hace uso de las librerias spring security y jjwt.

### Peticiones

* **Solicitar token**: En el codigo esta quemada la contraseña por lo que se requiere que sea **pass** para que se genere el token. El usuario puede ser cualquiera.
```
POST http://localhost:8080/login

Headers
Content-Type: application/json

Body
{
	"username": "brayan",
	"password": "pass"
}
```
*El token es generado con un rol especifico, según el rol dejara consumir el servicio de usuarios o administradores.*

* **Servicio solo para usuarios autenticados**: Enviar el token en el header Authorization.
```
GET http://localhost:8080/user

Headers
Authorization: Bearer token
```

* **Servicio solo para administradores autenticados**: Enviar el token en el header Authorization.
```
GET http://localhost:8080/admin

Headers
Authorization: Bearer token
```