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
    "Sacraments": [
      {
        "ID": "5943",
        "Name": "First Communion Date",
        "Description": "",
        "Value": ""
      },
      {
        "ID": "5944",
        "Name": "Test Field",
        "Description": "",
        "Value": ""
      }
    ]
  },
  "District": {
    "Enrollment Info": [
      {
        "ID": "4747",
        "Name": "Entrance Date",
        "Description": "",
        "Value": ""
      },
      {
        "ID": "4748",
        "Name": "Entrance Grade",
        "Description": "",
        "Value": ""
      }
    ]
  }
}
```
