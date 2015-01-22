# Family Lists

Retrieves a list of current families from the school

https://app.sycamoreeducation.com/api/v1/School/:SchoolID/Families

## GET

### Parameters

| Field | Description |
|-------|-------------|
| filter | String used to filter the list of families returned |
| Of | bar |
| Parameters | baz |

### Notes
- If no filter is given, all families that are marked for the current school year will be returned. Large results may be returned.
- The filter will match against any part of a families Name, Formal Name or Family Code (see example below)


### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID | Unique identifier of the family |
| Name | Full name of the family unit |
| Code | Sycamore's given family code |
| Address | Address of family |
| City 	| City the family lives in |
| State |	The state the family lives in |
| ZIP |	ZIP code for the family |
| HomePhone |	Listed home phone number for the family |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Families?filter=Bec

### Example Response
```json
[
    {
        "ID": "328432",
        "Name": "Beck, Glenn & Tania",
        "Code": "BEC1519",
        "Address": "1924 N. Clarkson Street",
        "City": "Fremont",
        "State": "NE",
        "ZIP": "68025",
        "HomePhone": "5552010000"
    },
    {
        "ID": "230",
        "Name": "Beckner, Aaron & Karen",
        "Code": "BEC1085",
        "Address": "909 West Alameda",
        "City": "Roswell",
        "State": "NM",
        "ZIP": "",
        "HomePhone": ""
    },
    {
        "ID": "330011",
        "Name": "Bonner, Bobby & Becky",
        "Code": "BON1523",
        "Address": "331 NE Hampton Ave",
        "City": "Omaha",
        "State": "NE",
        "ZIP": "68144",
        "HomePhone": "5553221661"
    }
]
```