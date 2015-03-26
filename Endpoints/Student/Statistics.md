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
| [Entity] | What entity the statistics are coming from: Local, District or State | 
| > [Group] | The name of the group for the following statistics |
| > > ID      | Unique idenitifer for this student statistic         |
| > > Name         | The name of the student statistic         |
| > > Description | A short description of the student statistic         |
| > > Value | The value given by the school for this statistic |

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/1232/Statistics

### Example Response
```json
{
  "Local": {
    "Personal": [
      {
        "ID": "1234",
        "Name": "Hair color",
        "Description": "What color is this persons hair",
        "Value": "brown"
      },
      {
        "ID": "2345",
        "Name": "Drivers License Number",
        "Description": "The 12 digit state drive license ID number",
        "Value": "H4543FF5565"
      }
    ]
  },
  "District": {
    "Enrollment Info": [
      {
        "ID": "3456",
        "Name": "Acceptance Date",
        "Description": "The date that this student was accepted into the district",
        "Value": ""
      },
      {
        "ID": "3457",
        "Name": "Accepted Grade",
        "Description": "The grade level that this student was accepted into",
        "Value": "6"
      }
    ]
  }
}
```
