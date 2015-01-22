# User Pass-A-Note Search

Retrieves a list of users who are eligable to receive Pass-A-Notes

https://app.sycamoreeducation.com/api/v1/User/:UserID/PAN/Search

## GET

### Parameters

| Field | Description |
|-------|-------------|
| filter | A string that will be compared to last name of a user to filter responses |
| type | The type of user you would like to search for. (1 = students, 2 = families, 3 = employees) Default: 3 |

### Notes
- School's have the ability to turn off the Pass-A-Note feature for students and families individually (would return 403 Forbidden if so)
- Families are not able tp PAN (and thus, search for) students
- Students are not able to PAN families and other students

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID 	|Unique identifier of the user |
| LastName |	The last name of the user|
| FirstName |	The first name of the user|

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/PAN/Search?type=1&filter=Fr

### Example Response
```json
[
    {
        "ID": "59805",
        "LastName": "Francisco",
        "FirstName": "Jose"
    },
    {
        "ID": "59806",
        "LastName": "Francisco",
        "FirstName": "Maria"
    },
    {
        "ID": "59807",
        "LastName": "Frye",
        "FirstName": "Autumn"
    },
    {
        "ID": "59808",
        "LastName": "Frye",
        "FirstName": "Taylor"
    }
]
```