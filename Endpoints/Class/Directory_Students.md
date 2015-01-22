# Class Directory (Student List)

Retrieves list of students who are currently enrolled in the specified class

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Directory

## GET

### Parameters

| Field | Description |
|-------|-------------|
| order |  Indicates which order the returned values should be ordered by (firstname or lastname) |

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID |	Unique ID associated with that student |
| Code | 	Sycamore School's student code for that student |
| ClassNumber |	Individual number give to that student within the specified class |
| FirstName | 	The student's first name |
| LastName | 	The student's last name |
| DOB | 	The given date of birth for the student (YYYY-MM-DD format) |
| NickName | 	The nickname for the student if any is provided |

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Directory

### Example Response
```json
[
    {
        "ID": "677887",
        "Code": "AAN1782-2",
        "ClassNumber": "0",
        "FirstName": "Jason",
        "LastName": "Aanerud",
        "DOB": "2013-08-19",
        "NickName": ""
    },
    {
        "ID": "387701",
        "Code": "ABE1571-2",
        "ClassNumber": "0",
        "FirstName": "Saraç Hailey",
        "LastName": "Abella",
        "DOB": "2006-03-27",
        "NickName": "Hailey"
    }

]
```