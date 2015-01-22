# Student Class Assignment Grades

Retrieves a list of graded assignments for the student

https://app.sycamoreeducation.com/api/v1/Student/:StudentID/Classes/:ClassID/Grades

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter  |	The academic quarter you'd like to pull classes from |
| schoolyearid  | The academic year that you'd like to pull grade postings from |
| limit | Limit the number of responses returned from the API |
| offset | Number of records to skip before starting the response |
| subjectid |	Filter for only returning a specific subset of grades that are attached to a subject |

### Notes
- If no school year is specified the current school year ID will be used
- If no quarter is specified the current quarter will be used
- Only grade postings that are marked 'Graded' inside of the system will be returned
- If you subject is specified, all assignments marked as 'Graded' will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID  | 	Unique identifier of the grade posting |
| Subject  | 	The name of the subject the assignment grade is tied to |
| Title  | 	The title of the assignment |
| DueDate  | 	The date which this assignment grade was due (should be past tense) |
| Possible  | 	Number of points the assignment was worth |
| Received  | 	Number of points the student was awarded |
| Score  | 	Number of points received out of points awarded |
| Comment  | 	A comment given by the teacher attached to this assignment grade |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085/Classes/58418/Grades

### Example Response
```json
[
    {
        "ID": "8211412",
        "Subject": "Math",
        "Title": "Qtr 3 Assignment",
        "DueDate": "01/31/13",
        "Possible": "100",
        "Received": "90",
        "Score": "90/100",
        "Comments": ""
    }
]
```