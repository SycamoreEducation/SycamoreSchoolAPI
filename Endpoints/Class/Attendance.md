# Class Attendance

Returns the necessary information for submitting classroom attendance

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Attendance

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter | The academic quarter you'd like to submit attendance for |
| date  | The date (YYYY-MM-DD format) that you'd like to select |

### Notes
- If no quarter is specified the current quarter will be used
- If no date is specified, the current date (UTC) will be used

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
|-------|-------------|
| Day |	Date of the attendance records being requests (mm/dd/yyyy format)
| Quarter | Quarter that the attendance records would fall into
| StudentCount | Total number of students eligible for attendance in this class
| Students | Object of individual students
| > ID | Unique ID for that student
| > ClassNumber | Unique number given to that student for that specific class
| > Code | Sycamore's code for that specific student
| > FirstName | The student's first name
| > LastName | The student's last name
| > NickName | The nickname given to the student if applicable
| Already |	Boolean value indicating whether attendance has already been taken for this class today
| AttendanceResult | Object of student IDs and the results of the attendance (null if Already = true)
| > Here | Indicates whether the student has an attendance record in the database or not
| > Hours |	Number of hours attendance counted towards (if school uses hours-based attendance)
| > Present | Floating point value indicating what part of the day the student was counted present
| > Absent | Floating point value indicating what part of the day the student was counted absent
| > Tardy | Boolean value indicating whether that student was counted tardy

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Attendance

### Example Response
```json
{
    "Day": "05 / 20 / 2014",
    "Quarter": "Q3",
    "StudentCount": 3,
    "Students": [
        {
            "ID": "677887",
            "ClassNumber": "",
            "Code": "AAN1782-2",
            "FirstName": "Jason",
            "LastName": "Aanerud",
            "NickName": ""
        },
        {
            "ID": "387701",
            "ClassNumber": "",
            "Code": "ABE1571-2",
            "FirstName": "Saraç Hailey",
            "LastName": "Abella",
            "NickName": "Hailey"
        },
        {
            "ID": "692503",
            "ClassNumber": "",
            "Code": "ACT1828-1",
            "FirstName": "Little",
            "LastName": "Account",
            "NickName": ""
        }
    ],
    "Already": "0",
    "AttendanceResults": null
}
```

## POST

### Parameters

| Field | Type | Description |
|-------|------|-------------|
| Date | String | Date (YYYY-MM-DD format) the attendance is submitted on. Default: Current date
| Students * | Array | An array of objects that with each key being a students unique ID
| > Tardy | Interger | Boolean (1/0) value indicating if the student was tardy. Default: 0
| > Absent | Interger |	Boolean (1/0) value indicating if the student was absent. Default: 0
| > Present | Interger | Boolean (1/0) value indicating if the student was tardy. Default: 0
| > ATID | Interger | Attendance type ID. Default: 0
| > Comment | String | Specific comments about this student's attendance record. Default: empty string

### Notes
- Must submit at least one student or a HTTP400 will be returned
- If attendance record already exists for a student, the POST will be ignored for that student
- HomeRoom detection happens automagically and will be inserted if needed
- Present, Absent and Tardy are not all required. All default to 0. Only the current status must be sent to correct take attendance.
- If Tardy is set to 1 for a POSTed record, Present = 1 will be assumed by the API as well, even if not explictly supplied.

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Students":  {
        "614085" : {
            "Present": 1,
            "Absent": 0,
            "Tardy": 1,
            "Comment": "This kid rocks!"
        }
    }
}
```

### Example Response
```json
{
    "Success": 1,
    "Created": 0,
    "Updated": 1
}
```
