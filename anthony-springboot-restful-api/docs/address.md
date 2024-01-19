# Address API Spec

## Create Address

Endpoint : POST /api/contacts/{idContact}/addresses

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "street" : "jalan apa",
  "city" : "kota",
  "province" : "provinsi",
  "country" : "negara",
  "postalcode" : "12313"
}
```

Response Body (Success) :

```json
{
  "data": {
    "id" : "randomstring",
    "street" : "jalan apa",
    "city" : "kota",
    "province" : "provinsi",
    "country" : "negara",
    "postalcode" : "12313"
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Contact is not found"
}
```

## Update Address

Endpoint : PUT /api/contacts/{idContact}/addresses/{idAddress}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "street" : "jalan apa",
  "city" : "kota",
  "province" : "provinsi",
  "country" : "negara",
  "postalcode" : "12313"
}
```

Response Body (Success) :

```json
{
  "data": {
    "id" : "randomstring",
    "street" : "jalan apa",
    "city" : "kota",
    "province" : "provinsi",
    "country" : "negara",
    "postalcode" : "12313"
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Address is not found"
}
```

## Create Address

Endpoint : 

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success) :

Response Body (Failed) :

## Get Address

Endpoint :

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success) :

Response Body (Failed) :

## Remove Address

Endpoint :

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success) :

Response Body (Failed) :

## List Address

Endpoint :

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success) :

Response Body (Failed) :