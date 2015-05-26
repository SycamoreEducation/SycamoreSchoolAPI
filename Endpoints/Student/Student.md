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
| NickName | The defined "nick name" of the student |
| DOB | The Date of Birth of the student |
| MedInfo | Current medical alert for the student |
| Picture | A partial URL to the location of this students photo |
| Email | The student's email address |
| Cell | The cell phone number of the student |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085

### Example Response
```json
{
  "Code": "KIR2341-1",
  "FirstName": "Analease",
  "LastName": "Kirkey",
  "NickName": "AK",
  "DOB": "2012-12-08",
  "MedInfo": "",
  "Picture": "614085/1395360179078.jpg",
  "Email": "test@gmail.com",
  "Cell": "(555) 555-1717"
}
```
