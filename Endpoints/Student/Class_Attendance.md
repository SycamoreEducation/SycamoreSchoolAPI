# Student Classroom Attendance

Returns the details of a students attendance for a particular class

https://app.sycamoreeducation.com/api/v1/Student/134/Classes/1223/Attendance

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter | The academic quarter you would like to see returned data from |

### Notes
- If no quarter is specified, the current quarter (or the nearest quarter if there isn't one current) will be used

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Date      | The Date (YYYY-MM-DD) that the attendance record was taken |
| Homeroom | Boolean (1/0) value indicating if this is a homeroom or not         |
| Present | Float value indicating the percentage of the class the sudent was marked present         |
| Absent | Float value indicating the percentage of the class the sudent was marked absent         |
| Tardy | Boolean (1/0) value indicating if the student was marked as tardy        |
| Excused | Boolean (1/0) value indicating if the student was marked as excused absent         |
| Unexcused | Boolean (1/0) value indicating if the student was marked as unexcused absent         |
| Notes | Any attendance specific notes that were entered with the students record |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/1234/Classes/5678/Attendance

### Example Response
```json
[
  {
     "Date": "2014-06-06",
     "Homeroom": "1",
     "Present": "0.75",
     "Absent": "0.25",
     "Tardy": "0",
     "Excused": "0",
     "Unexcused": "0",
     "Notes": ""
  },
  {
     "Date": "2014-06-19",
     "Homeroom": "1",
     "Present": "1.00",
     "Absent": "0.00",
     "Tardy": "1",
     "Excused": "0",
     "Unexcused": "0",
     "Notes": ""
   }
]
```
