# Students

Returns a list of students that are related to thes chool

https://app.sycamoreeducation.com/api/v1/School/1002/Students

## GET

### Parameters

| Field | Description |
|-------|-------------|
| typeid | The unique ID of the Student Type requested  |
| grade | Return students who are apart of this numerical grade |
| filter | A string that is used to filter students by their last name |

### Notes
- Only students marked "Current" inside of the system will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | Unqiue identifier for this student |
| FamilyID   | The unique identified for this student's family |
| UserID | The unique identifier for this students user account (0 if not enabled)|
| StudentCode | The student code given to the student by Sycamore School |
| FirstName | The first name of the student |
| LastName | The last name of the student |
| Grade | The numerical grade of the student |
| GradYear | The year the student is graduating |
| Graduated | Boolean value indicating if the student has graduated or not 

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Students?grade=3

### Example Response
```json
[
  {
    "ID": "962163",
    "FamilyID": "302023",
    "UserID": "0",
    "StudentCode": "AND1498-5",
    "FirstName": "Tiffany",
    "Lastname": "Anderson",
    "Grade": "3",
    "GradYear": "0",
    "Graduated": "0"
  },
  {
    "ID": "1012593",
    "FamilyID": "111327",
    "UserID": "0",
    "StudentCode": "BAN1360-4",
    "FirstName": "Jacob",
    "Lastname": "Banks",
    "Grade": "3",
    "GradYear": "0",
    "Graduated": "0"
  }
]
```
