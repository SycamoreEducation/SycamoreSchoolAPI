# School Safety Alert

Retrieves the active safety alert from the school

https://app.sycamoreeducation.com/api/v1/School/:schoolid/SafetyAlert

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID   | 	The unique identifier for this Safety Alert |
| Type   | 	The type of safety alert that has been issued |
| Message   | 	The text or instructions that accompany the alert |
| Created   | 	The datetime that this safety alert was created |
| Dismissed 	  | Boolean value indicating if the user has dismissed the alert |
| Users *  | Object of each user who has acknowledged the safety alert |
| > FirstName   | 	The first name of the user |
| > LastName 	  | The last name of the user |
| > DateTime   | 	The datetime that the user acknowledged the alert |
| > Dismissed   | 	Boolean value indicating if the user has dismissed the alert from their computer |

### Notes
- The Safety Alerty will be acknowledged when a user visits the endpoint
- The Users object will only be returned if the user accessing the endpoint has the Superuser scope

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/SafetyAlert

### Example Response
```json
{
    "Type": "Lock Down",
    "Message": "Mr. Green is in the building.",
    "Created": "2014-06-27 20:52:02",
    "Users": {
        "FirstName": "Joe",
        "LastName": "Cool",
        "DateTime": "2014-06-27 16:02:00",
        "Dismissed": "1"
    }
}
```