# Class Assignment (Details)

Retrieves the details of a single assignments

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Assignments/:AssignmentID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
|-------|-------------|
| GroupID | 	The assignment group that this assignment belongs to| 
| CategoryID | 	The weighted class assignment category that this assignment belongs to| 
| Title | 	The title of the assignment| 
| Status | 	The status of the assignment (1=current, 2=graded, 3=future)| 
| SubjectID | 	The subject that this assignment is in (only applicable for Daylong classses)| 
| Quarter | 	The academic quarter that this assignment falls in| 
| Dropbox | 	Boolean value indicated if this assignment has dropbox enabled| 
| Possible | 	The number of points that this assignment is worth| 
| DueDate | 	The date this assignment is/was due (MM/DD/YYYY format)| 
| Grades | 	Object of entries for any grades that have already been given for this assingment| 
| > ID | 	Unique identifier for the student that this grade record belongs to| 
| > Score | 	The numeric score given for the assignment| 
| > Comments | 	Any comments given by the teacher when issuing grades| 
| > Status | Interger indicating the assignment status for this student. -1 = Absent, -2 = Dropped, 1 = Excused,  3 = Missing, 4 = Late |

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Assignments/2243171

### Example Response
```json
{
    "GroupID": "0",
    "CategoryID": "90343",
    "Title": "macbeth essay",
    "Status": "2",
    "SubjectID": "20509",
    "Quarter": "3",
    "Dropbox": "0",
    "Possible": "100",
    "DueDate": "11/04/2012",
    "Grades": [
        {
            "ID": "677887",
            "Score": "100",
            "Comments": "Great job!",
            "Status": "-1"
        }

        {
            "ID": "342345",
            "Score": "75",
            "Comments": "You missed the mark!",
            "Status": "0"
        }
    ]
}
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
|Graded |	Boolean |	Indicates if you'd like this assignment moved to "Graded" after submitting grades
|Students * | 	Array |	An array with each key being a students unique ID
|> Score |	Interger |	The numeric score that the student receives on the assignment
|> Comments | 	String  |	Textual comments added to the assignment grade by the teacher
|> Status |	Interger |	Which status the assignment is given for that student. -1 = Absent, -2 = Dropped, 1 = Excused, 3 = Missing, 4 = Late. Default: 0 |


### Notes
- * denotes required field
- If a grade record already exists for a student, the record will be updated
- Class activity logs will be updated on a successful request

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Students": {
        "614085": {
            "Score": "99",
            "Status": "4",
            "Comments": "You Rule!"                    
        }
    }    
}
```

### Example Response
```json
{
    "Success": 1,
    "Created": 1,
    "Updated": 0
}
```