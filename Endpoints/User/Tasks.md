# User Tasks

Retrieves a list of tasks created and owned by a user

https://app.sycamoreeducation.com/api/v1/User/:UserID/Tasks

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | 	The number of memos that will be returned |
| offset | 	Number of records to skip before starting the response |

### Notes
- All tasks are returned ordered by priority
- The 'limit' paramater's default is 10 and the 'offset' paramater's default is 0

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID  |	Unique identifier of the task | 
| Title | 	The title of the task given by the user |
|DueDate |	The date given when this task is due to be completed |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/Tasks?limit=3

### Example Response
```json
[
    {
        "ID": "4875",
        "Title": "Got to get it done!",
        "DueDate": "August 13, 3:06 pm"
    },
    {
        "ID": "8953",
        "Title": "Bootstrap IT UP!",
        "DueDate": "June 13, 8:59 pm"
    },
    {
        "ID": "4876",
        "Title": "Jumping jacks",
        "DueDate": "August 16, 3:07 pm"
    }
]
```