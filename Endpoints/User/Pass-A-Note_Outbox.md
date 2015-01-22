# User Pass-A-Notes Outbox

Retrieves a list of Pass-A-Notes that have been sent by the user

https://app.sycamoreeducation.com/api/v1/User/:UserID/PAN/Outbox

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | The number of memos that will be returned |
| offset | Number of records to skip before starting the response |

### Notes
- The 'limit' paramater's default is 10 and the 'offset' paramater's default is 0

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID  | 	Unique identifier of the Pass-A-Note |
| Subject  | 	The title of the Pass-A-Note |
| Date 	 | The date that the PAN was sent |
| Recipients  | 	An object with an entry for each user who recieved this Pass-A-Note |
| > ToID  | 	The User ID of the user who recieved the PAN |
| > ToName  | 	Name of the user who recieved the PAN |
| > Delievered  | 	Boolean value indicating if the message has been succesfully delivered |
| > Closed  | 	Boolean value indiciating if the message has been seen and closed by the user |
| > Deleted  | 	Boolean value indicating if the message has been deleted by the user |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/PAN/Outbox?limit=2

### Example Response
```json
[
    {
        "ID": "10510692",
        "Subject": "RE(1): Sycamore Code Camp",
        "Date": "Tue, Jun 17 7:57 PM",
        "Recipients": [
            {
                "ToID": "212436",
                "ToName": "Jose & Regina Cantdoate",
                "Delivered": "0",
                "Closed": "0",
                "Deleted": "0"
            }
        ]
    },
    {
        "ID": "10510690",
        "Subject": "Non-Stop",
        "Date": "Tue, Jun 17 7:55 PM",
        "Recipients": [
            {
                "ToID": "166513",
                "ToName": "Nick  Schreck",
                "Delivered": "0",
                "Closed": "0",
                "Deleted": "0"
            }
        ]
    }
]
```