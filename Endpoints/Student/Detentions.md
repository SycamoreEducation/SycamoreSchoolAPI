# Student Detentions

Returns a list of detentions that have been assigned to a particular student

https://app.sycamoreeducation.com/api/v1/Student/:studentID/24343/Detentions

## GET

### Notes
- School's have the ability to disable the student/family viewing of discipline logs. A 403 Forbidden will be returned with a note stating "Your school has disabled viewing of discipline logs." if this is the case.

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | Unique ID of the detention         |
| Author         | Name of staff member who issued this detentions         |
| Created | The date that this dentention was created |
| Served | The date that this detention was served (if applicable) |
| Completed | Boolean value indicating if the detention has been served or not | 

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/43453/Detentions

### Example Response
```json
[
  {
    "ID": "71239",
    "Created": "03/06/15",
    "Served": "03/13/15",
    "Completed": "1",
    "Author": "Brock Ellis"
  }
]
```
