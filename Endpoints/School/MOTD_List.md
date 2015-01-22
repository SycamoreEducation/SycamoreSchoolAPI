# Message of the Day (list)

Retrieves a list of the Messages of the Day for the school

https://app.sycamoreeducation.com/api/v1/School/:schoolID/MOTD

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | Limit the number of responses returned from the API |
| offset | Number of records to skip before starting the response |

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID | 	Unique ID field for the MotD returned |
| Title | The title of the MotD |
| Date | Date (YYYY-MM-DD) that the Message of the Day is assigned to |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/MOTD?limit=3

### Example Response
```json
[
    {
        "ID": "17499",
        "Title": "State Basketball",
        "Date": "2015-10-03"
    },
    {
        "ID": "17501",
        "Title": "Chili Cookoff!",
        "Date": "2015-06-27"
    },
    {
        "ID": "17460",
        "Title": "This is a test",
        "Date": "2014-06-06"
    }
]
```