# User Task

Retrieves details about a specific task

https://app.sycamoreeducation.com/api/v1/User/:UserID/Tasks/:TaskID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
|-------|-------------|
| Title |	The 'title' given to the task by the user  |
| Description| 	The content of the task |
| Priority 	|The descriptor of how important this task is to the user |
| Status  | The user-given to the specific task |
| DueDate |	The date that has been specified for this task to be completed |
| Updated |	Date and time this task was last updated |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/Tasks/4875

### Example Response
```json
{
    "Title": "Got to get it done!",
    "Description": "My backyard... oi",
    "Priority": "High",
    "Status": "In Progress",
    "DueDate": "August 13, 3:06 pm",
    "Updated": "August 5, 3:07 pm"
}
```