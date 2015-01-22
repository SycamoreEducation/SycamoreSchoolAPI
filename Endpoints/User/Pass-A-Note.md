# User Pass-A-Note

Retrieves the details of a Pass-A-Notes that has been sent to the user

https://app.sycamoreeducation.com/api/v1/User/:UserID/PAN/:PanID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| FromID   | 	The unique identifier of the user who sent this Pass-A-Note |
| From   | 	The username of the user who sent this Pass-A-Note |
| Subject   | 	The title of the Pass-A-Note |
| Message   | 	The content of the Pass-A-Note |
| Date 	  | The date that the Pass-A-Note was sent to the user |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/PAN/10463899

### Example Response
```json
{
    "FromID": "45345",
    "From": "Stephen Hawking",
    "Subject": "The purpose of life",
    "Message": "Hello there! The purpose of life is to enjoy the small things. Hope this helps!",
    "Date": "Wed, May 21 8:07 PM"
}
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Subject | String |	The subject of the Pass-A-Note |
| Message * | 	String 	|The message body of the Pass-A-Note |

### Notes
- * denotes required field
- If no subject is given, the original PAN subject will be used and a "RE(#)" field will be prepended
- On a successful request, an attempt will be made to notify the user of their Pass-A-Note instantly via the Instant PAN feature

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Message": "Yes, I believe little Timmy would be just a little too young to appreciate the Code Camp. Maybe next year!"
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

https://app.sycamoreeducation.com/api/v1/User/834534/PAN/10463899

### Example Response
```json
{
    "success": 1,
}
```