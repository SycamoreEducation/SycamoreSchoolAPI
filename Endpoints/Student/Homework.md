# Student Homework

Retrieves a list of current assignments that a student should be working on as homework

https://app.sycamoreeducation.com/api/v1/Student/:StudentID/Homework

## GET

### Parameters

| Field | Description |
|-------|-------------|
| subjectid | The class subject you'd like to limit responses from |

### Notes
- If no subjectid is given all assignments will be returned
- Only assignments labeled "Current" within the system will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ClassID |	The unique ID for a class |
| ClassName | 	The name given to the class |
| Title |	Title give for the homework assignment |
| DueDate |	Date that this assignment will be due for completion |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085/Homework

### Example Response
```json
[
    {
        "ClassID": "58418",
        "ClassName": "3rd Grade - Thompson",
        "Title": "Qtr 3 Assignment",
        "DueDate": "01/31/13"
    },
    {
        "ClassID": "148787",
        "ClassName": "Computer Mediated Communication",
        "Title": "Computer Basics",
        "DueDate": "06/11/12"
    },
    {
        "ClassID": "148787",
        "ClassName": "Computer Mediated Communication",
        "Title": "Facebook and the Fall of Conversations",
        "DueDate": "02/25/13"
    },
    {
        "ClassID": "148787",
        "ClassName": "Computer Mediated Communication",
        "Title": "Dropbox Test",
        "DueDate": "07/16/13"
    }
]
```