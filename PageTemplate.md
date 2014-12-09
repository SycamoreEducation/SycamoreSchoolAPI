# Title

Description of the endpoint goes here

https://app.sycamoreeducation.com/api/v1/School/1002

## GET

### Parameters

| Field | Description |
|----------------------|
| Table | foo |
| Of | bar |
| Parameters | baz |

### Notes
- List
- of
- notes

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
|----------------------|
| Table | foo |
| Of | bar |
| Parameters | baz |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002

### Example Response
```json
{
    "Returned": "foo",
    "JSON": "bar",
    "Values": "baz",
}
```

## POST

### Parameters

| Field | Type | Description |
|----------------------|
| Table | String | foo |
| Of | Interger | bar |
| Parameters | Boolean | baz |

### Notes
- List
- of
- notes

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Data": "foo",
    "ToBe": "bar",
    "POSTed": "baz",
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/School/1002/News/433425"
}
```

## DELETE

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002

### Example Response
```json
{
    "Success": 1,
}
```
