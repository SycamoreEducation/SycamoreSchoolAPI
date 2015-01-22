# Student Missing Assignment

Retrieves a list of  assignments that are marked as 'missing' for a student

https://app.sycamoreeducation.com/api/v1/School/1002

## GET

### Parameters

| Field | Description |
|-------|-------------|
| subjectid | The class subject that you'd like to limit responses from |

### Notes
- If no subjectid is specified, all assignments will be returned
- Only assignments graded with a status of "Missing" within the system will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ClassID 	|The unique ID for a class |
| ClassName | 	The name given to the class |
| Title |	Title give for the homework assignment |
| DueDate | 	Date that this assignment will be due for completion |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085/Missing

### Example Response
```json
[
    {
        "ClassID": "58418",
        "ClassName": "3rd Grade - Thompson",
        "Title": "Subject Verb Agreement",
        "DueDate": "05/21/14"
    }
]
```