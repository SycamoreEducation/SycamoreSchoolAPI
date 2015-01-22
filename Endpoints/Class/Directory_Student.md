# Class Directory (Individual Student)

Retrieves class level details of a specified student

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Directory/:StudentID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Code 	|Sycamore School's student code for that student|
| FirstName |	The student's first name|
| LastName |	The student's last name|
| DOB 	|The given date of birth for the student (YYYY-MM-DD format)|
| NickName |	The nickname for the student if any is provided|
| MedInfo |	Medical Alerts for the student if any|
| Picture |	Name of picture file for the student|
| Email |	Email address for the student|
|Cell  |	Cell phone number for the student|

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Directory/435

### Example Response
```json
{
    "Code": "BEC1085-4",
    "FirstName": "Esther",
    "LastName": "Beckner",
    "DOB": "2001-09-04",
    "NickName": "Esty",
    "MedInfo": "No Medical Alerts",
    "Picture": "Ester_Beckner.jpg",
    "Email": "ebeckner@gmail.com",
    "Cell": "(612) 392-5969"
}
```