# Student osted Grades

Retrieves a list of posted grades for the student

https://app.sycamoreeducation.com/api/v1/Student/:StudentID/Grades

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter | The academic quarter you'd like to pull classes from | 
| schoolyearid | The academic year that you'd like to pull grade postings from |

### Notes
- If no school year is specified the current school year ID will be used
- If no quarter is specified the current quarter will be used
- Only grade postings that are marked 'Viewable' inside of the system will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID  | 	Unique identifier of the grade posting |
| ClassID  | 	The unique ID for a class |
| ClassName  | 	The name given to the class |
| SubjectID  | 	Unique identifier of the subject the grade posting is for |
| SubjectName  | 	The name given to the subject |
| Number  | 	The numeric grade the student recieved |
| Letter  | 	The letter grade the student recieved for the grade posting |
| Comment  | 	A comment given by the teacher attached to this grade posting |
| Viewable  | 	Boolean value designating if this grade should be viewable or not |
| PDate 	 | The date that this grade posting was created |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085/Grades?quarter=4

### Example Response
```json
[
    {
        "ID": "22726291",
        "ClassID": "148787",
        "ClassName": "Computer Mediated Communication",
        "SubjectID": "0",
        "SubjectName": null,
        "Number": "100",
        "Letter": "P",
        "Comments": "Aren't you amazing!",
        "Viewable": "1",
        "PDate": "11/18/13"
    },
    {
        "ID": "22616330",
        "ClassID": "199806",
        "ClassName": "Delete Test",
        "SubjectID": "59129",
        "SubjectName": "English",
        "Number": "85",
        "Letter": "B",
        "Comments": "You're Awesome Blossom!",
        "Viewable": "1",
        "PDate": "11/14/13"
    }
]
```