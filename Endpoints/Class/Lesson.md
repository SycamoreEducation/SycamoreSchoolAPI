# Class Lesson Plan

Retrieves details about a specified lesson plan

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Lessons/:LessonID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| SubjectID |	The ID of the subject that this lesson plan is tied to |
| Unit |	Curriculum unit that this lesson plan belongs to |
| Completed | 	Boolean value indicating if this lesson plan has already been taught |
| Title |	The title of the lesson plan |
| Date |	The date (MM/DD/YYYY) the lesson plan is assigned to |
| Objectives | 	The content for the objectives of the lesson plan |
| Resources |	The content for the resources of the lesson plan |
| Procedures  |	The content for the procedures of the lesson plan |
| Evaluation  |	The content for the evaluation of the lesson plan |
| Notes 	 |The content for the notes of the lesson plan |
| Homework  |	The content for the homework of the lesson plan |
|Subject  |	The name of the subject this lesson plan is tied to |

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Lessons/1305287

### Example Response
```json
{
    "SubjectID": "32324",
    "Unit": "1",
    "Completed": "0",
    "Title": "Test lesson plan",
    "Date": "06/19/2014",
    "Objectives": "The learner will be able to accomplish XYZ after this lesson",
    "Resources": "Text book and online handout",
    "Procedures": "Will talk about it in class in lecture format",
    "Evaluation": "Formal quiz",
    "Notes": "Be careful about stating any specifics about anything",
    "Homework": "Problems 4-6 on page 43",
    "Subject": "U.S History B "
}
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Title | 	String | 	The title of the lesson plan| 
| Unit | 	Interger | The curriculum unit that this lesson plan is tied to. Default: 0| 
| Date | 	Date (YYYY-MM-DD) | 	The date that this assignment is due. Default: Current date| 
| SubjectID | 	Interger | 	The ID of the class subject for the assignment. Default: 0| 
| Objectives | 	Text | 	The content for the objectives of the lesson plan| 
| Resources | 	Text | 	The content for the resources of the lesson plan| 
| Procedures | 	Text | 	The content for the procedures of the lesson plan| 
| Evaluation | 	Text | 	The content for the evaluation of the lesson plan| 
| Notes 	| Text|  	The content for the notes of the lesson plan| 
| Homework | 	Text | 	The content for the homework of the lesson plan| 
| Completed | 	Boolean (1/0) | Indicate if the lesson plan has already been taught. Default: 0| 

### Notes
- All fields are optional

### Returns

On Success: HTTP/1.1 200 OK

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Unit": "1",
    "Notes": "Be careful about stating any specifics about anything",
    "Homework": "Problems 4-6 on page 43",
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/Class/58418/Lessons/1305287"
}
```

## DELETE

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Lessons/1305287

### Example Response
```json
{
    "Success": 1
}
```