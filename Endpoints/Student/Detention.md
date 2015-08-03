# Student Detention

Returns the details of a specific detention for a student

https://app.sycamoreeducation.com/api/v1/Student/:studentID/Detentions/:detentionID

## GET

### Notes
- School's have the ability to disable the student/family viewing of discipline logs. A 403 Forbidden will be returned with a note stating "Your school has disabled viewing of discipline logs." if this is the case.
- of
- notes

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Created      | The date that the detention was created         |
| Served      | The date that the detention was served (if applicable)         |
| Completed         | Boolean value indicating if the detention was completed         |
| Length | The duration (in minutes) of this detention          |
| Comments | Any comments left by the staff at the school about this detention |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/3454/Detentions/5467

### Example Response
```json
{
    "Length": "45",
    "Comments": "Come watch bubble guppies!",
    "Created": "2015-03-06",
    "Served": "2015-03-13",
    "Completed": "1",
    "Author": "Brock Ellis",
    "Monitor": "Brock Ellis"
}
```
