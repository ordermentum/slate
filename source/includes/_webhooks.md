
# Webhooks

## Get All Webhooks

```shell
curl "https://api.ordermentum.com/v1/webhooks"
  -H "Authorization: Bearer UNIQUE_TOKEN"
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "totalResults": 10,
    "totalPages": 1,
    "pageSize": 25,
    "pageNo": 1
  },
  "links": {
    "self": "https://app.ordermentum.com/v1/products?supplierId=a5cad00b-0c85-4d95-ab3f-9fb1933dbeed&pageNo=3",
    "first": "https://app.ordermentum.com/v1/products?supplierId=bd4b8236-1649-49a5-aa6e-2d0f0e9407ea&pageNo=1",
    "prev": "https://app.ordermentum.com/v1/products?supplierId=44c2ae51-b2eb-4f86-b021-fc7d181f5b65&pageNo=2",
    "next": "https://app.ordermentum.com/v1/products?supplierId=561b48a5-f292-4f5c-abfe-3d7ff70ee91b&pageNo=4",
    "last": "https://app.ordermentum.com/v1/products?supplierId=5331fea9-52e3-427d-bae8-57f1b7c7edd8&pageNo=9"
  },
  "data": [
  ]
}
```

This endpoint retrieves all webhooks.

### HTTP Request

`GET http://app.ordermentum.com/v1/webhooks`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
pageNo | 1 | Page number
pageSize | 25 | Number of webhooks in the response
retailerId | null | The retailer to retreive the webhooks for
supplierId | null | The supplier to retreive the webhooks for


## Create a Webhook

```shell
curl "http://app.ordermentum.com/v1/webhook"
  -H "Authorization: Bearer UNIQUE_TOKEN"
  -X POST
  -D '{}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "b1da7ace-824e-4e69-8463-f0c70d7fac0b",
  "name": "Inventory Service",
  "supplierId": "503be8e5-15cb-4aa1-bf9b-15c28dff0fb4",
  "events": ["invoice_created", "invoice_updated"],
  "createdAt": "2016-12-01T05:44:59.223Z",
  "createdBy": "cb8898d9-6072-4e2a-be8a-44409606322c",
  "updatedAt": "2016-12-01T05:44:59.223Z",
  "deletedAt": "2016-12-01T05:44:59.223Z",
  "updatedBy": "2e5bdba0-a650-4bb5-a2c1-5eb7a20d1f5d"
}
```

This endpoint retrieves a specific webhook.

## Get a Specific Webhook

```shell
curl "http://app.ordermentum.com/v1/webhooks/69B34C71-3D61-4D40-92DE-BD7954D26BD2"
  -H "Authorization: Bearer UNIQUE_TOKEN"
```

> The above command returns JSON structured like this:

```json
{
  "id": "b1da7ace-824e-4e69-8463-f0c70d7fac0b",
  "name": "Order - #OM155",
  "createdAt": "2016-12-01T05:44:59.223Z",
  "createdBy": "cb8898d9-6072-4e2a-be8a-44409606322c",
  "updatedAt": "2016-12-01T05:44:59.223Z",
  "deletedAt": "2016-12-01T05:44:59.223Z",
  "updatedBy": "2e5bdba0-a650-4bb5-a2c1-5eb7a20d1f5d"
}
```

This endpoint retrieves a specific webhook.

### HTTP Request

`GET http://app.ordermentum.com/v1/webhooks/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the webhook to retrieve

## Update a specific webhook

```shell
curl "http://app.ordermentum.com/v1/webhooks/9AD783F1-4E1E-4396-A317-D528C99E177D"
  -X PUT
  -D '{"name": "Test Webhook" }'
  -H "Authorization: UNIQUE_TOKEN"
```

> The above command returns JSON structured the same a GET request

This endpoint updates a specific webhook

### HTTP Request

`PUT http://app.ordermentum.com/webhooks/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the webhook to update

## Delete a specific webhook

```shell
curl "http://app.ordermentum.com/v1/webhooks/9AD783F1-4E1E-4396-A317-D528C99E177D"
  -X DELETE
  -H "Authorization: UNIQUE_TOKEN"
```

> The above command returns JSON structured the same a GET request

This endpoint deletes a specific webhook

### HTTP Request

`DELETE http://app.ordermentum.com/v1/webhooks/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the webhook to delete
