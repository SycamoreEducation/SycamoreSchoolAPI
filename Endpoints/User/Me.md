# Me

Returns specific details about the user attached to the access token

https://app.sycamoreeducation.com/api/v1/Me

## GET

### Notes
- This endpoint servers as a great place to look for user-specific information before prompting the user for their data (i.e. query this endpoint to check if they have an email before prompting the user to enter their email)


### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Parameters

| Field | Description |
|----------------------|
| UserID | Unique identifier of the user
| SchoolId | Unique identifier of the school that the user belongs to
| FirstName | The first name of the user
| LastName | The last name of the user
| Email | Given email address of the user
| FamilyID | Unique identifier of the family this user belongs to (0 if none)
| StudentID | Unique identifier of the student this user ID is attached to (0 if none)
| Level | Current permission level the user has within Sycamore School
| SuperUser | Boolean value declaring whether or not the user is a "Super User" of the school
| Active | Boolean value denoting if the user is labeled 'active' within the system
| Current |Boolean value declaring whether or not the user is labeled 'current' inside of the system

### Example Request

https://app.sycamoreeducation.com/api/v1/Me

### Example Response
```json
{
    "UserID": "342322",
    "SchoolID": "1002",
    "FirstName": "John",
    "LastName": "Smith",
    "Email": "jsmith@youdontknowjack.com",
    "FamilyID": "0",
    "StudentID": "0",
    "Level": "2",
    "SuperUser": "1",
    "Active": "1",
    "Current": "1"
}
```
