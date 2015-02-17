# Student Statistic

Retrieve a single student statistic for a student.

https://app.sycamoreeducation.com/api/v1/Student/1234/Statistics/4343

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Name         | The name of the student statistic         |
| Description | A short description of the student statistic         |
| Value | The value given by the school for this statistic |
| Type | The type of statistic this is. 1 = text, 2 = multiple choice, 3 = date |
| Sequence | The order in which this statistic appears in the group list | 

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/1232/Statistics/23423

### Example Response
```json
{
  "Name": "Math Level",
  "Description": "Math Level",
  "Value": "Algebra",
  "Type": "2",
  "Sequence": "40"
}
```
