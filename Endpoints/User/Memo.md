# User Memo

Retrieves details about a specific memo

https://app.sycamoreeducation.com/api/v1/User/:UserID/Memos

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit |	The number of memos that will be returned |
| offset |	Number of records to skip before starting the response|

### Notes
- All memos are returned in reverse chronilogical order (newest at the beginning)
- The 'limit' paramater's default is 10 and the 'offset' paramater's default is 0

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Subject |	The 'title' given to the memo by the user |
| Content | 	The content of the memo |
| Date | 	The date that the memo was last updated |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/Memos/7440

### Example Response
```json
{
    "Title": "New API Versioning!",
    "Content": "YAY!",
    "Date": "August 8, 7:41 pm"
}
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Subject | 	String |	The 'title' given to the memo by the user |
| Content |	String |	The content of the memo |

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Subject": "New Hobby",
    "Content": "I like roller blading!"
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/User/1337/Memos/34234543"
}
```

## DELETE

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request

https://app.sycamoreeducation.com/api/v1/User/87585/Memos/1305287

### Example Response
```json
{
    "Success": 1,
}
```