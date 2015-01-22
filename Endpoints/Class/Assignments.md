# Class Assignments (List)

Retrieves list of assignments for the specified class

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Assignments

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter | The academic quarter you'd like to select assignments from |
| status | The graded status of the assignments you'd like to see. (1=current, 2=graded, 3=future) |
| subjectid | The class subject used to filter returned assigments |

### Notes
- If no quarter is specified the current quarter will be used
- If no status is specified all assigments will be returned
- subjectid is only applicable to Daylong classes

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
|ID | 	Unique ID associated with that assignment |
|GroupID | 	The assignment group that this assignment belongs to|
|CategoryID | 	The weighted class assignment category that this assignment belongs to|
|Title |	The title of the assignment|
|Status |	The status of the assignment (1=current, 2=graded, 3=future)|
|SubjectID | 	The subject that this assignment is in (only applicable for Daylong classses)|
|Subject |	The formal name of the subject for the assignment|
|Quarter |	The academic quarter that this assignment falls in|
|Dropbox |	Boolean value indicated if this assignment has dropbox enabled|
|DueDate |	The date this assignment is/was due (MM/DD/YYYY format)|

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Assignments

### Example Response
```json
[
    {
        "ID": "8425360",
        "GroupID": "31112",
        "CategoryID": "202003",
        "Title": "Facebook and the Fall of Conversations",
        "Status": "1",
        "SubjectID": "0",
        "Quarter": "3",
        "Dropbox": "0",
        "DueDate": "02/25/2013"
    },
    {
        "ID": "8425381",
        "GroupID": "31112",
        "CategoryID": "202003",
        "Title": "Twitter and Grammar",
        "Status": "2",
        "SubjectID": "0",
        "Quarter": "3",
        "Dropbox": "0",
        "DueDate": "02/25/2013"
    }
]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Title *    | String | 	The title of the assigment|
| Quarter |	Interger |The academic quarter this assignment falls into. Default: Current quarter|
|DueDate |	Date (YYYY-MM-DD)| 	The date that this assignment is due. Default: Current date|
|SubjectID |	Interger |	The ID of the class subject for the assignment. Default: 0|
|CategoryID |	Interger |	The ID of the class grading category for the assignment. Default: 0|
|GroupID | Interger |	The ID of the assignment group for the assignment. Default: 0|
|Description |	String| 	The text/instructions of the assignment. Default: null|
|Points |	Interger| 	How many points are possible to earn. Default: 0|
|Unit |	Interger |	The class curriculum unit ID for the assignment. Default: 0|
|Status |	Interger | Which status the assignment will initially have. (1=current, 2=graded, 3=future) Defaults: 3. |
|DropBox |	Boolean (1/0) |	Indicate if the assignment will be dropbox enabled. Default: 0|
|Calendar |	Boolean (1/0) | Indicate whether or not this assignment is viewable on the class calendar. Default: 0|

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
    "Title": "Differential Equations",
    "Quarter": "3",
    "Unit": "2",
    "DueDate": "2014-06-19",
    "Description": "Read pg 54-58 and do questions #1-7",
    "Points": "15",
    "Status": "1",
    "Calendar": "1",
    "DropBox": "0"
}
```

### Example Response
```json
{
    "Success": 1,
    "location": "https://app.sycamoreeducation.com/api/v1/Class/148787/Assignments/11904013"
}
```