# Student Discipline Logs

Retrieves a list of discipline logs for a specific student

https://app.sycamoreeducation.com/api/v1/Student/:studentID/DisciplineLogs

## GET

### Notes
- School's have the ability to disable the student/family viewing of discipline logs. A 403 Forbidden will be returned with a note stating "Your school has disabled viewing of discipline logs." if this is the case.

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | Unique ID of the particular discipline log         |
| Violation | The textual title of the school created discipline violation         |
| Points | Integer representing the point value of the violation |
| Author | The name of the school staff who created the log |
| Date | The date (YYYY-MM-DD) that the log was created |
| Quarter | The academic quarter that the discipline log was created in |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/124555/Discipline

### Example Response
```json
[
  {
    "ID": "427684",
    "Points": "3",
    "Date": "2015-01-12",
    "Quarter": "3",
    "Author": "Brock Ellis",
    "Violation": "Misbehavior"
  },
  {
    "ID": "449692",
    "Points": "5",
    "Date": "2015-02-26",
    "Quarter": "3",
    "Author": "Brock Ellis",
    "Violation": "Disrespect"
  }
]
```
