# Class

Retrieves information about an individual class

https://app.sycamoreeducation.com/api/v1/School/:SchoolID/Classes/:ClassID

## GET

### Notes
- Only classes that are marked as "public" within the system will be returned
- "CategoryID" and "Category" will only ever return for Period Long classes

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID  | 	Unique identifier of the class |
| SharedClassID  | 	The unique ID for a class that shares information |
| Name  | 	The name given to the class |
| Section  | 	Section number of the class (potentially not unique) |
| Description  | 	Description give to the class by the school |
| DepartmentID | The unique ID of the department this class belongs to |
| Department | The name of the department this class belongs to |
| CategoryID | The unique ID of the District/Diocese category this class belongs to |
| Category | The name of the category that this class belongs to |
| HomeRoom  | 	A boolean value to signify if the class is considered a homeroom or not |
| PeriodID  | 	The unique ID of the period that this class takes place in |
| PrimaryStaffID | The unique ID of the primary staff member for this class |
| PrimaryTeacher | The name of the primary staff member for this class |
| Public  | 	A boolean value to signify is this class should be makde public |
| Term | The term length of this class |
| ParentAccess |  	A boolean value that describes whether or not the school has disabled parent access to the class |
| Facility  | 	Object that contains data about the facility this classroom is assigned to |
| > ID  | 	The unique ID of the facility assigned to this class |
| > Name  | 	The name that has been given to this facility |
| > Number  | 	The identifying number that has been given to this facility (may not be unique) |
| Location  | 	Object that contains data about the location this classroom is assigned to |
| > ID  | The unique ID of the location assigned to this class |
| > Name  | 	The name that has been given to this location |
| > Number  | 	The identifying number that has been given to this location(may not be unique) |
| Teachers  | 	Object that contains information about the teachers that are listed for this class |
| > ID  | 	The unique ID for the teacher's user |
| > FirstName  | 	First name of the teacher |
| > LastName  | 	Last name of the teacher |
| > GoesBy  | 	Listed 'nick name' or 'alias' for the teacher |
| > ClassStatus  | 	The teacher's class-specific status (set inside of the Sycamore School Classroom) |
| Gradebook  | 	Object that contains information about the grade book for this class |
| > Subjects  | 	Array that contains information about the subjects in the grade book for this class |
| > > ID  | 	Unique ID for this specific subject |
| > > Name  | 	Name of the subject |
| > > Description  | 	Description of the subject |
| > Categories  | 	Array that contains information about the weighted grade categories for the grade book |
| > > ID  | 	Unique ID for this specific grade category |
| > > Name  | 	Name of the grade category |
| > > Percentage  | 	Whole number percentage for this specific category |
| > Groups  | 	Array that containts information about the categorization groups used in the grade book |
| > > ID  | 	Unique ID for this assignment category |
| > > Name  | 	Name of the assignment category |
| > > Description  | 	Description of the assignment category |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Classes/58418

### Example Response
```json
{
    "ID": "58418",
    "SharedClassID": "0",
    "Name": "3rd Grade - Thompson",
    "Section": "2",
    "Description": "3rd Grade - Thompson",
    "HomeRoom": "1",
    "PeriodID": "7188",  
    "Facility": {
        "ID": "672",
        "Name": "Cafeteria",
        "Number": "10"
    },
    "Location": {
        "ID": "708",
        "Name": "Rudolph",
        "Number": "0"
    },
    "Public": "1",
    "ParentAccess": "1"
    "Gradebook": {
        "Subjects": [
            {
                "ID": "56267",
                "Name": "Accelerated Reader",
                "Description": ""
            },
            {
                "ID": "20509",
                "Name": "English",
                "Description": ""
            },
            {
                "ID": "48695",
                "Name": "Math",
                "Description": ""
            }
        ],
        "Categories": [
            {
                "ID": "90343",
                "Name": "Assignments",
                "Percentage": "80"
            },
            {
                "ID": "116788",
                "Name": "Test",
                "Percentage": "10"
            },
            {
                "ID": "329581",
                "Name": "Participation",
                "Percentage": "10"
            }
        ],
        "Groups": [
            {
                "ID": "31958",
                "Name": "TTC",
                "Description": "A Tale of Two Cities"
            },
            {
                "ID": "31959",
                "Name": "Hound",
                "Description": "Hound of the Baskervilles"
            }
        ]
    }
}
```
