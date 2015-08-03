# Student Discipline Log

Retrieves the details of a specific discipline log for a student

https://app.sycamoreeducation.com/api/v1/Student/:studentID/Discipline/:disciplineID

## GET

### Notes
- School's have the ability to disable the student/family viewing of discipline logs. A 403 Forbidden will be returned with a note stating "Your school has disabled viewing of discipline logs." if this is the case.
- Not all Discipline Logs include a "Victim" field. The field will be returned if there are values present.

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Date | The date (YYYY-MM-DD) that the log was created |
| Violation | The title of the school created discipline violation         |
| Points | Integer representing the point value of the violation |
| Author | The name of the school staff who created the log |
| Created | The datetime (YYYY-MM-DD H:i:s) that the log was created |
| Description | The textual description of the discipline violation as recorded by staff |
| Quarter | The academic quarter that the violation took place in |
| Resolution | The text entered by the staff describing how th violation was handeled |
| Victim | The name of the student who was in the victim role during this violation |
| ManagerNotified | Boolean value indiciating whether a note was sent to the Discipline Manager about this log |
| FamilyNotified | Boolean value indiciating whether a note was sent to the student's family about this log |
| StudentNotified | Boolean value indiciating whether a note was sent to the student about this log |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/124555/Discipline/3425676

### Example Response
```json
{
    "Date": "2015-01-25",
    "Violation": "Talking Back",
    "Points": "3",
    "Author": "Brock Ellis",
    "Created": "2015-01-25 15:23:12",
    "Quarter": "3",
    "Description": "Were coloring on the walls with crayon.",
    "Resolution": "Made them wash it off.",
    "ManagerNotified": "0",
    "FamilyNotified": "0",
    "StudentNotified": "0",
}
```
