# Student Attendance

Returns an overview of a particular student's attendance

https://app.sycamoreeducation.com/api/v1/Student/1234/Attendance

## GET

### Notes
- Individual attendance records are cleared out yearly. Only the current school years attendance records are available.

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | The unique identifier of the class         |
| ClassName         | The name of the class         |
| Section | The section designation that has been given to this class         |
| Homeroom | Boolean value (1/0) for if this class is considered a homeroom |
| TotalDay | The total number of days attendance records we have for the student in this class |
| Tardies | The number of times the student has been counted tardy |
| Absences | The number of time the student has been counted absent |
| Present | The number of time the student has been counted present |
| Hours | The number of classroom hours the student has been present |
| Percentage | The percentage of time the student has been present ((total days / present) * 100) | 


### Example Request

https://app.sycamoreeducation.com/api/v1/Student/1234/Attendance

### Example Response
```json
[
  {
      "ID": "58418",
      "ClassName": "3rd Grade - Thompson",
      "Section": "002",
      "Homeroom": "1",
      "TotalDays": "30",
      "Tardies": "10",
      "Absences": "6.75",
      "Present": "22.25",
      "Hours": "0.00",
      "Percentage": "74"
  },
  {
      "ID": "148787",
      "ClassName": "Computer Mediated Communication",
      "Section": "01",
      "Homeroom": "0",
      "TotalDays": "20",
      "Tardies": "6",
      "Absences": "4.00",
      "Present": "16.00",
      "Hours": "0.00",
      "Percentage": "80"
  }
]
```
