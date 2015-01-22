# Family Students

Retrieves a list of students that belong to the specified family

https://app.sycamoreeducation.com/api/v1/Family/:FamilyID/Students

## GET

### Parameters

| Field | Description |
|-------|-------------|
| schoolyearid | The academic year that you'd like to pull current students from |

### Notes
- If no schoolyearid is specified the current school year ID will be used

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID | Unique identifier of the student |
| Code | 	The Sycamore given code for the student |
| FirstName | 	First name of the student |
| LastName | 	Last name of the student |
| Grade |	The title of the grade the student is currently enrolled in |
| DOB |	The date of birth of the student (YYYY-MM-DD format) |
| Gender | 	One letter indicator of the gender of the student (M for male, F for female) |

### Example Request

https://app.sycamoreeducation.com/api/v1/Family/647150/Students

### Example Response
```json
[
    {
        "ID": "453453",
        "Code": "ROM3432-1",
        "FirstName": "Jennifer",
        "LastName": "Bixby",
        "Grade": "8th Grade",
        "DOB": "2002-12-08",
        "Gender": "F"
    }
]
```