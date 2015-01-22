# User Pass-A-Notes

Retrieves a list of Pass-A-Notes that have been sent to the user

https://app.sycamoreeducation.com/api/v1/User/:UserID/PAN

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | 	The number of memos that will be returned |
| offset | 	Number of records to skip before starting the response |
| preview | 	Returns the first 30 characters of the Pass-A-Note |
| unread | 	Boolean value indicating if you want just a total of unread messaging returned |

### Notes
- The 'limit' paramater's default is 10 and the 'offset' paramater's default is 0
- If unread=1 is passed through, only the Unread count will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID 	 | Unique identifier of the Pass-A-Note |
| FromID  | 	The unique identifier of the user who sent this Pass-A-Note |
| From  | 	The username of the user who sent this Pass-A-Note |
| Subject  | 	The title of the Pass-A-Note |
| Date  | 	The date that the Pass-A-Note was sent to the user |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/PAN?limit=3

### Example Response
```json
[
    {
        "ID": "10463899",
        "FromID": "342",
        "From": "Sprint Guy",
        "Subject": "Can you hear me?",
        "Date": "Wed, May 21 8:07 PM"
    },
    {
        "ID": "9830022",
        "FromID": "3242346",
        "From": "The Joker",
        "Subject": "Hello, BATMAN",
        "Date": "Fri, Jan 31 6:04 PM"
    },
    {
        "ID": "9655677",
        "FromID": "6565653",
        "From": "Jessi Sexton",
        "Subject": "Testing",
        "Date": "Tue, Dec 24 4:04 PM"
    }
]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Subject * | String | 	The subject of the Pass-A-Note |
| Message * |	String |  The content body of the Pass-A-Note |
| ToUID * |	Interger | 	The unique User ID of the intended recipient |

### Notes
- * denotes required field
- On a successful request, an attempt will be made to notify the user of their Pass-A-Note instantly via the Instant PAN feature

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Subject": "Four twernty-one",
    "Message": "This is a message",
    "ToUID": "87585"
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/School/1002/News/433425"
}
```