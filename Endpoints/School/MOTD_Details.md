# Message of the Day (details)

Retrieves the details of a Messages of the Day

https://app.sycamoreeducation.com/api/v1/School/:schoolID/MOTD/:motdID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Title | The title of the MotD |
| Date 	| Date (YYYY-MM-DD) that the Message of the Day is assigned to |
| Message  |	The content of the Message of the Day |
| Color | The hex color that has been assigned to this MotD |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/MOTD/17460

### Example Response
```json
{
    "Title": "This is a test",
    "Date": "2014-06-06",
    "Message": "This is a test 1 2 3",
    "Color": "CC3366"
}
```