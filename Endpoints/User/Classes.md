# User Class Lists

Retrieves a list of classes that the user is labeled a 'teacher' in

https://app.sycamoreeducation.com/api/v1/User/:UserID/Classes

## GET

### Parameters

| Field | Description |
|-------|-------------|
| quarter | The academic quarter you'd like to pull classes from |
| type |The type of class you'd like to return (1 = Day Long, 2 = Period Long, 3 = General, 4 = Preschool) |

### Notes
- If no type is specified, all classes will be returned (there may be a delay in response due to potentially large volume of results)
- If no quarter is specified the current quarter will be used- notes
- This endpoint is meant to return the list of classes a user is labeled a 'teacher' in (for viewing student's classes, use the Student/Classes endpoint)

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
| Public 	 | A boolean value to signify is this class should be makde public | 
| ParentAccess 	 | A boolean value that describes whether or not the school has disabled parent access to the class | 

### Example Request

https://app.sycamoreeducation.com/api/v1.0/User/87585/Classes?type=2

### Example Response
```json
{
    "Period": [
        {
            "ID": "28541",
            "SharedClassID": "0",
            "Name": "11th Grade",
            "Section": "",
            "Description": "11th Grade Homeroom",
            "HomeRoom": "1",
            "PeriodID": "5",
            "FacilityID": "674",
            "Public": "0",
            "ParentAccess": "1"
        },
        {
            "ID": "148787",
            "SharedClassID": "0",
            "Name": "Computer Mediated Communication",
            "Section": "01",
            "Description": "Computer Mediated Communication",
            "HomeRoom": "0",
            "PeriodID": "7193",
            "FacilityID": "22",
            "Public": "1",
            "ParentAccess": "1"
        },
        {
            "ID": "218699",
            "SharedClassID": "0",
            "Name": "Innovation 101",
            "Section": "001",
            "Description": "Innovation 101",
            "HomeRoom": "0",
            "PeriodID": "7194",
            "FacilityID": "3305",
            "Public": "0",
            "ParentAccess": "1"
        },
        {
            "ID": "144835",
            "SharedClassID": "0",
            "Name": "Sycamore Education 101",
            "Section": "",
            "Description": "Sycamore Education 101",
            "HomeRoom": "0",
            "PeriodID": "0",
            "FacilityID": "3305",
            "Public": "0",
            "ParentAccess": "1"
        }
    ]
}
```