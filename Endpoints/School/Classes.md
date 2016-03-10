# Class Lists

Retrieves a list of classes defined

https://app.sycamoreeducation.com/api/v1/School/1002/Classes

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter | The academic quarter you'd like to pull classes from (0 = all available) |
| roster | Include a list of IDs of students in each class (1 = include) |
| type | The type of class you'd like to return (1 = day long, 2 = period long, 3 = general, 4 = preschool) |

### Notes
- If no type is specified, all classes will be returned (may be delay in respinse due to potentially large volume)
- If no quarter is specified the current quarter will be used

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID 	 | Unique identifier of the class |
| SharedClassID  | 	The unique ID for a class that shares information |
| Name  | 	The name given to the class |
| Section  | 	Section number of the class (potentially not unique) |
| Description  | 	Description give to the class by the school |
| HomeRoom  | 	A boolean value to signify if the class is considered a homeroom or not |
| PeriodID  | 	The unique ID of the period that this class takes place in |
| FacilityID  | 	The unique ID of the facility assigned to this class |
| Public  | 	A boolean value to identify if this class should be listed in the school's "class directory" |
| ParentAccess  | 	A boolean value that describes whether or not the school has disabled parent access to the class |

### Example Request

https://app.sycamoreeducation.com/api/v1.0/School/1002/Classes?type=2&roster=1

### Example Response
```json
{
    "Period": [
        {
            "ID": "219",
            "SharedClassID": "0",
            "Name": "English 101",
            "Section": "ENG101",
            "Description": "Introduction to modern English",
            "HomeRoom": "0",
            "PeriodID": "7188",
            "PrimaryStaffID": "59096",
            "FacilityID": "0",
            "Public": "0",
            "ParentAccess": "1",
            "Roster": [],
            "PrimaryTeacher": "John Doe",
            "TermLength": "Second"
        },
        {
            "ID": "152180",
            "SharedClassID": "0",
            "Name": "#010-三甲 中文注音 週日",
            "Section": "",
            "Description": "#010 - 三甲 中文注音 週日, 3A Chinese Traditional Sunday",
            "HomeRoom": "0",
            "PeriodID": "7",
            "PrimaryStaffID": "22984",
            "FacilityID": "9550",
            "Public": "0",
            "ParentAccess": "0",
            "Roster": ["243259","830680","677963","243694","280907","161662","113168","88534","481","895497"],
            "PrimaryTeacher": "John Doe",
            "TermLength": "Second"
        }

    ]
}
```
