# User Memos

Retrieves a list of memos created and owned by a user

https://app.sycamoreeducation.com/api/v1/User/:UserID/Memos

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | 	The number of memos that will be returned |
| offset | 	Number of records to skip before starting the response|

### Notes
- All memos are returned in reverse chronilogical order (newest at the beginning)
- The 'limit' paramater's default is 10 and the 'offset' paramater's default is 0

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID |	Unique identifier of the memo |
| Subject | 	The title of the memo given by the user |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/Memos?limit=3

### Example Response
```json
[
    {
        "ID": "7440",
        "Subject": "New API Versioning!"
    },
    {
        "ID": "7434",
        "Subject": "New Memo"
    },
    {
        "ID": "6791",
        "Subject": "Adrian Peterson"
    }
]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Subject  | 	String  | The title of the memo |
| Note  | String 	|The content of the memo |

### Notes
- One of the two paramaters must be present for the POST to be successful else a 400 will be returned

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Subject": "The New Way",
    "Note": "This is the new way to create memos"
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/User/87585/Memos/8441"
}
```