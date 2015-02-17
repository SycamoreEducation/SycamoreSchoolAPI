# Student Statistics

Retrieve a list of all, or groups, of a student's statistics.

https://app.sycamoreeducation.com/api/v1/Student/1234/Statistics

## GET

### Parameters

| Field | Description |
|-------|-------------|
| groupid | The statistic group identifier that will be used to limit results returned  |

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | Unique idenitifer for this student statistic         |
| Name         | The name of the student statistic         |
| Description | A short description of the student statistic         |
| Value | The value given by the school for this statistic |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/1232/Statistics

### Example Response
```json
{
  "No Group": [
    {
      "ID": "3552",
      "Name": "Handedness",
      "Description": "What is the students",
      "Value": "Both"
    },
    {
      "ID": "3578",
      "Name": "Option Enrollment?",
      "Description": "Out or In",
      "Value": "OptIn"
    }
  ],
  "Sacraments": [
    {
      "ID": "2385",
      "Name": "Communion",
      "Description": "",
      "Value": "No"
    },
    {
      "ID": "3963",
      "Name": "Attending Church",
      "Description": "What church do they attend? Where is the church located and who is the patron Saint? Why did they pick that church?",
      "Value": "STPatrick"
    }
  ]
}
```
