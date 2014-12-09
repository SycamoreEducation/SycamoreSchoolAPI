# Classes

Retrieves a list of classes that a student is enrolled in

https://app.sycamoreeducation.com/api/v1/Student/:StudentID/Classes

## GET

### Parameters

| Field | Description |
|----------------------|
| quarter * | The academic quarter you'd like to pull classes from
| schoolyearid * | The academic year that you'd like to pull grade postings from
| type * | The type of class you'd like to return

### Notes
- Types are:
  1. Day Long
  2. Period Long
  3. General
  4. Preschool
- If no school year is specified the current school year ID will be used
- If no quarter is specified the current quarter will be used
- Schools may choose to disable access to student schedules for either families or students which would cause a 401 Unauthorized error to be returned
- Classes may be excluded if they are marked 'Not Parent/Student Accessible' within the system

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
|----------------------|
| ID | Unique identifier of the grade posting
|Name | The name given to the class
|Description | Description give to the class
|HomeRoom | Boolean value to declare if this class is considered a 'home room' class
|PeriodID | The unique identifier for the school day period that this class takes place in
|Section | The section number for the class
|FacilityID | Unique identifier for the room that is used by this class
|Public | A boolean value to signify is this class should be makde public
|PDate | A boolean value that describes whether or not the school has disabled parent access to the class

### Example Request

https://app.sycamoreeducation.com/api/v1/Student/614085/Classes

### Example Response
```json
{
    "Daylong": [
        {
            "ID": "58418",
            "Name": "3rd Grade - Thompson",
            "Description": "3rd Grade - Thompson",
            "HomeRoom": "1",
            "PeriodID": "7188",
            "Section": "2",
            "FacilityID": "0",
            "Public": "1",
            "ParentAccess": "1"
        },
        {
            "ID": "199806",
            "Name": "Delete Test",
            "Description": "Delete Test",
            "HomeRoom": "0",
            "PeriodID": "7188",
            "Section": "101",
            "FacilityID": "24",
            "Public": "0",
            "ParentAccess": "1"
        }
    ],
    "Period": [
        {
            "ID": "148787",
            "Name": "Computer Mediated Communication",
            "Description": "Computer Mediated Communication",
            "HomeRoom": "0",
            "PeriodID": "7193",
            "Section": "01",
            "FacilityID": "22",
            "Public": "1",
            "ParentAccess": "1"
        }
    ]
}
```
