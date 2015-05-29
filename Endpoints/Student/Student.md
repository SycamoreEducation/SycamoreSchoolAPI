# Student Details

Retrieves the details about a specific student

https://app.sycamoreeducation.com/api/v1/Student/:StudentID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
|-------|-------------|
| Code | The student  code given to the student by Sycamore School |
| FirstName | The first name of the student |
| LastName | The last name of the student |
| Ethnicity | The enthnicity of the student |
| NickName | The defined "nick name" of the student |
| DOB | The Date of Birth of the student |
| MedInfo | Current medical alert for the student |
| Picture | A partial URL to the location of this students photo |
| Email | The student's email address |
| Cell | The cell phone number of the student |
| AdvisorID | The unique User ID for the student's advisor |
| Advisor | The name of the student's advisor |
| HomeroomTeacherID | The unique User ID for the student's homeroom teacher |
| HomeroomTeacher | The name of the student's homeroom teacher |
| LockerNum | The students locker num |
| ComboNum | The students combination number for their locker |
| StateID | The students state-given ID number | 
| ExtID | The students External ID number |
| Gender | Representation of the student's gender (M or F) |
| Grade | The grade that the student is in |


### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085

### Example Response
```json
{
    "Code": "ELL1727-1",
    "FirstName": "Ansleigh",
    "LastName": "Ellis",
    "Ethnicity": "Non Hispanic/Latino",
    "NickName": "Baby A",
    "DOB": "2012-12-08",
    "Picture": "614085/1395360179078.jpg",
    "Email": "brock@sycamoreleaf.com",
    "Cell": "(402) 253-1949",
    "AdvisorID": "166513",
    "HomeroomTeacherID": "87585",
    "Gender": "F",
    "Grade": "Preschool",
    "ExtID": "1234",
    "StateID": "1337",
    "LockerNum": "1337",
    "ComboNum": "1085",
    "Advisor": "Nick  Schreck",
    "HomeroomTeacher": "Brock Ellis"
}
```
