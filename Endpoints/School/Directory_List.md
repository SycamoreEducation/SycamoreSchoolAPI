# School Directory (Families)

Retrieves a list of families and their basic contact information

https://app.sycamoreeducation.com/api/v1/School/:schoolid/Directory/:string

## GET

### Parameters

| Field | Description |
|-------|-------------|
| Table | foo |
| Of | bar |
| Parameters | baz |

### Notes
- Families must be enabled to appear in the directory
- Individual families may opt out of sharing information (address, phone #, email) through the directory
- The :string value is used to filter families by last name
- The :string value can either be a alphabetical letter or search string, e.g. "Adki" would return "Adkins" and "Adkinson"

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID |	Unique ID field for the record returned |
| Name |	Common name for the family |
| Address1 |	First line of family address |
| Address2 | Second line of family address |
| State |	State the family resides in |
| ZIP |	ZIP code of family address |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Directory/S

### Example Response
```json
[
    {
        "ID": "233",
        "Name": "Saferite, Matt & Beth",
        "Address1": "56 e. palm beach",
        "Address2": "",
        "State": "KS",
        "ZIP": "34545"
    },
    {
        "ID": "647218",
        "Name": "SAMPLE, Joe"
    },
    {
        "ID": "239",
        "Name": "Sampson, Glenn",
        "Address1": "76 Burgundy Lane",
        "Address2": "",
        "State": "MO",
        "ZIP": ""
    }
]
```