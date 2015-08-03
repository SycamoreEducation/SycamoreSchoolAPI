# School Discipline Logs

Retuns back a listing of all the discipline logs for the school for a given day

https://app.sycamoreeducation.com/api/v1/School/1002

## GET

### Parameters

| Field | Description |
|-------|-------------|
| Date | The date (YYYY-MM-DD) that you would like returned |

### Notes
- If no date is given, today's date is used as the filter

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | Unique ID of the discipline log         |
| Violation       | The title of the discipline log violation         |
| StudentID | The unique ID of the student that this discipline log applies to         |
| StudentCode | The student's code  for this discipline log |
| Student | The name of the student that this discipline log applies to |
| Grade | The grade that this student is enrolled in |
| Author | The name of the staff member who created this discipline log |
| Description | The text description given by the school for this type of violation |
| Points | The point value for this discipline violation |
| Created | The datetime (YYYY-MM-DD HH:MM:SS) when this log was created |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002

### Example Response
```json
[
  {
    "ID": "492136",
    "StudentID": "717474",
    "StudentCode": "INQ1958-3",
    "Student": "Jacob Inquiry",
    "Grade": "7th",
    "Violation": "Issue Noted"
    "Description": "test",
    "Points": "0",
    "Created": "2015-07-27 14:34:12",
    "Author": "Micheline Sherrod",
    "Points": "3"
  }
]
```
