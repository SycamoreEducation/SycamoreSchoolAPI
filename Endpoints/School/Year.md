# School Year

Retrieves the details about a specific school year

https://app.sycamoreeducation.com/api/v1/School/:schoolid/Years/:schoolyearid

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Current   | 	Boolean value indicating if this is the current school year |
| Name   | 	The given name for this school year |
| Description   | 	The description of this school year |
| EndDate | The date and this school year ends |
| Q1 | An object for the first quarter's details |
| > StartDate | The date that Q1 begins |
| > Days | The number of academic school years in Q1 |
| Q2 | An object for the first quarter's details |
| > StartDate | The date that Q2 begins |
| > Days | The number of academic school years in Q2 |
| Q3 | An object for the first quarter's details |
| > StartDate | The date that Q3 begins |
| > Days | The number of academic school years in Q3 |
| Q4 | An object for the first quarter's details |
| > StartDate | The date that Q4 begins |
| > Days | The number of academic school years in Q4 |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Years/209953

### Example Response
```json
{
    "Current": "1",
    "Name": "2014-2015",
    "Description": "2014-2015 School Year",
    "EndDate": "2015-06-08",
    "Q1": {
        "StartDate": "2014-06-02",
        "Days": "70"
    },
    "Q2": {
        "StartDate": "2014-09-08",
        "Days": "73"
    },
    "Q3": {
        "StartDate": "2014-12-08",
        "Days": "57"
    },
    "Q4": {
        "StartDate": "2015-03-09",
        "Days": "65"
    }
}
```
