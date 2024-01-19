# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "name": "Nasi Rendang",
  "tutorialLink": "https://www.youtube.com/watch?v=4AnRfHEupsY", // provide any youtube link
  "area": "Padang, Indonesia",
  "descriptions": "Ini pedas, ini enak, ini mantul",
  "ingredients": [
    {
      "name": "Nasi",
      "amount": 1,
      "unit": "piring"
    },
    {
      "name": "Rendang",
      "amount": 3,
      "unit": "potong"
    },
    {
      "name": "Sambal",
      "amount": 3,
      "unit": "sendok"
    }
  ]
}
```

Response Body (Success) :

```json
{
  "isOk": true,
  "data": {
    "id": "a6f0b9a8-3c5a-11ec-9c0a-0242ac130002",
    "name": "Nasi Rendang",
    "tutorialLink": "https://www.youtube.com/watch?v=4AnRfHEupsY",
    "area": "Padang, Indonesia",
    "descriptions": null,
    "ingredients": [
      {
        "name": "Nasi",
        "amount": 1,
        "unit": "piring"
      },
      {
        "name": "Rendang",
        "amount": 1,
        "unit": "piring"
      },
      {
        "name": "Sambal",
        "amount": 1,
        "unit": "piring"
      }
    ]
  }
}
```
Response Body (Failed) :

```json
{
  "isOk": false,
  "errorCode": 1000, // See Error Code List
  "reason": "Missing Field 'ingredients' "
}
```

## Login User

Endpoint : POST /api/auth/login

Request Body :

```json
{
  "username" : "anthony",
  "password" : "secret"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "token" : "TOKEN",
    "expiredAt" : 232434234235 //milliseccond
  }
}
```
Response Body (Failed, 401) :

```json
{
  "errors" : "Username or Password Wrong"
}
```

## Get User

Endpoint : GET /api/users/current

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data" : {
    "username" : "anthony",
    "name" : "Anthony" 
  }
}
```
Response Body (Failed, 401) :

```json
{
  "errors" : "Unauthorized"
}
```

## Update User

Endpoint : PATCH /api/users/current

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "name" : "Anthony",
  "password" : "new password"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "anthony",
    "name" : "Anthony" 
  }
}
```
Response Body (Failed, 401) :

```json
{
  "errors" : "Unauthorized"
}
```

## LogOut User

Endpoint : DELETE /api/auth/logout

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data" : "OK"
}
```