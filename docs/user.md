# User API Docs

## Register User Endpoint

- POST "/api/users"

Request Body :
```json
{
    "username" : "voxxyg",
    "password" : "pass123",
    "name" : "Prayoga Danuarta"
}
```

Response Body Success :

```json
{
    "data": {
        "username" : "voxxyg",
        "name" : "Prayoga Danuarta"
    },
}
```

Response Body Error :

```json
{
    "errors" : "Username already registered",
}
```

## Login User Endpoint

- POST : "api/users/login"

Request Body :

```json
{
    "username" : "voxxyg",
    "password": "pass123"
}
```

Response Body Success :

```json
{
    "data": {
        "token" : "unique-token"
    } 
}
```

Response Body Error :

```json
{
    "errors" : "Username or password wrong"
}
```

## Update User Endpoint

- PATCH : "/api/users/current"

Headers : 
- Authorization : token

Request Body : 

```json
{
    "name" : "voxxyg again", //optional
    "password" : "newPass123" // optional
}
```

Resposne Body Success
```json
{
    "data" : {

        "name" : "voxxyg again",
        "password" : "newPass123" 
    }
}
```

Resposne Body Error

```json
{
    "errors" : "name length max 100"
}
```
## Get User Endpoint

- GET : "/api/users/current"

Headers: 
- Authorization : token

Response Body Success :

```json
{
    "data" : {
        "username" : "voxxyg",
        "name": "Prayoga Danuarta
    }
}
```

Response Body Error
```json
{
    "errors" : "Unauthorized"
}
```
## Register User Endpoint

- DELETE : "/api/users/logout"

Headers : 
- Authorization : token

Response Body Success :
```json
{
    "data" : "OK"
}
```

Response Body Error :
```json
{
    "errors" : "Unauthorized"
}
```