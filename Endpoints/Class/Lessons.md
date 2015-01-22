# Class Lesson Plans (List)

Retrieves list of lesson plans for the specified class

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Lessons

## GET

### Parameters

| Field | Description |
|-------|-------------|
| start | The date (YYYY-MM-DD) used as the ending point for selecting records |
| end | The date (YYYY-MM-DD) used as the ending point for selecting records |
| subjectid |	The class subject used to filter returned assigments |

### Notes
- If not start date is supplied, only future lesson plans will be returned
- subjectid is only applicable to Daylong classes
- Lessons are sorted by Date and SubjectID (where applicable)

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID |	Unique ID associated with that lesson plan |
| SubjectID | 	The ID of the subject that this lesson plan is tied to|
| Title |	The title of the lesson plan|
| Date |	The date (MM/DD/YYYY) the lesson plan is assigned to|
| Subject | 	The name of the subject this lesson plan is tied to|

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Lessons

### Example Response
```json
[
    {
        "ID": "1305222",
        "SubjectID": "48695",
        "Topic": "Polynomials",
        "Date": "06/26/2014",
        "Subject": "Math"
    },
    {
        "ID": "1305223",
        "SubjectID": "48695",
        "Topic": "Polynomials",
        "Date": "06/27/2014",
        "Subject": "Math"
    }
]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Title * |  String | The title of the lesson plan |
| Unit |	Interger | The curriculum unit that this lesson plan is tied to. Default: 0 |
| Date |	Date (YYYY-MM-DD)  |		The date that this assignment is due. Default: Current date |
| SubjectID | 	Interger 	 |	The ID of the class subject for the assignment. Default: 0 |
| Objectives |	Text  |		The content for the objectives of the lesson plan |
| Resources |	Text  |		The content for the resources of the lesson plan |
| Procedures | 	Text  |		The content for the procedures of the lesson plan |
| Evaluation | 	Text  |		The content for the evaluation of the lesson plan |
| Notes |	Text  |		The content for the notes of the lesson plan |
| Homework | 	Text |	The content for the homework of the lesson plan |
| Completed |	Boolean (1/0) | 	Indicate if the lesson plan has already been taught. Default: 0 |
| AllWeek | Boolean (1/0) | 	Indicate if one lesson plan per day needs to be created for the week. Default: 0 |

### Notes
- * denotes required field
- Class activity logs will be updated on a successful request

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Title": "Test lesson plan",
    "Date": "2014-06-19",
    "Unit": "1",
    "SubjectID": "32324",
    "Objectives": "The learner will be able to accomplish XYZ after this lesson",
    "Resources": "Text book and online handout",
    "Procedures": "Will talk about it in class in lecture format",
    "Evaluation": "Formal quiz",
    "Notes": "Be careful about stating any specifics about anything",
    "Homework": "Problems 4-6 on page 43",
    "Completed": "0",
    "AllWeek": "0"
}
```

### Example Response
```json
{
    "Success": 1,
    "location": "https://app.sycamoreeducation.com/api/v1/Class/58418/Lessons/1305287"
}
```