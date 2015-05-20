# School Years

Retrieves a list of school years created by the school

https://app.sycamoreeducation.com/api/v1/School/:schoolid/Years

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID   | 	The unique identifier for this school year |
| Current   | 	Boolean value indicating if this is the current school year |
| Name   | 	The given name for this school year |
| Description   | 	The description of this school year |
| StartDate 	  | The date that this school year begins |
| EndDate | The date and this school year ends |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Years

### Example Response
```json
[
  {
    "ID": "211486",
    "Current": "0",
    "Name": "2016-2017",
    "Description": "2016-2017 School Year",
    "StartDate": "2016-08-01",
    "EndDate": "2016-08-01"
  },
  {
    "ID": "210515",
    "Current": "0",
    "Name": "2015-2016",
    "Description": "2015-2016 School Year",
    "StartDate": "2015-06-08",
    "EndDate": "2016-06-10"
  },
  {
    "ID": "209953",
    "Current": "1",
    "Name": "2014-2015",
    "Description": "2014-2015 School Year",
    "StartDate": "2014-06-02",
    "EndDate": "2015-06-08"
  }
]
```
