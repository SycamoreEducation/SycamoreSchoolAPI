# School Employees

Returns back all employees for a specific school

https://app.sycamoreeducation.com/api/v1/School/1002/Employees

## GET

### Parameters

| Field | Description |
|-------|-------------|
| typeid | The numeric ID of a User Type that all returned employees would belong to |
| filter | A string used to filter results based on the employee's last name  |

### Notes
- Only Employees marked as 'current' wil be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID      | The unique ID of the employee         |
| FirstName         | The first name of the employee         |
| LastName | The last name of the employee         |
| Directory | Boolean value indicating if this employee should be included in the employee directory |
| UserStatus | A user-defined string indicating their current status in the system |
| LocationID | Unique ID of physical employment location for employee |
| HomePhone | The home phone number for the employee |
| CellPhone | The cell phone number for the employee |
| WorkPhone1 | The primary work phone number for the employee |
| WorkPhone2 | The secondary work phone number for the employee |
| FaxPhone | The fax line number for the employee |
| Title | The formal title of the employee |
| Email1 | Primary email address for the employee |
| Email2 | Secondary email address for the employee |
| Active | Boolean value indicating if the employee should be active or not |
| Current | Boolean value indicating if the employee is current or not (should be 1) |
| PositionID | The unique ID of the position the employee holds at the school |
| ManangerID | The unique user ID of the manager of this employee |
| Level | What level the user holds in this school (1=Volunteer, 2=Emplyoee, 3=Supervisor, 4=Administrator) |
| Address1 | First address line for the employee |
| Address2 | Second address line, if applicable, for the employee |
| City | City of residence for the employee |
| State | State of residence for the employee |
| ZIP | ZIP code of residence for the employee |
| Country | Country of residence for the employee |
| Position | Name of position indicated by PositionID |
| Manager | Name of manager indicated by ManagerID |
| Location | Name of location indicated by LocationID |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Employees?filter=Jo

### Example Response
```json
[
  {
    "ID": "171144",
    "FirstName": "Sam",
    "LastName": "Jones",
    "Directory": "1",
    "UserStatus": "OnLine",
    "LocationID": "7",
    "HomePhone": "",
    "CellPhone": "",
    "WorkPhone1": "",
    "WorkPhone2": "",
    "FaxPhone": "",
    "Title": "",
    "Email1": "sjones@gmail.com",
    "Email2": "",
    "Active": "1",
    "Current": "1",
    "PositionID": "27",
    "ManagerID": "16992",
    "Level": "2",
    "Address1": "",
    "Address2": "",
    "City": "",
    "State": "",
    "Zip": "",
    "Country": "",
    "Position": "Supervisor",
    "Manager": "John Smith",
    "Location": "Main Building"
  },
  {
    "ID": "368739",
    "FirstName": "Tammy",
    "LastName": "Jones",
    "Directory": "1",
    "UserStatus": "New Employee",
    "HomePhone": "245-235-2452",
    "CellPhone": "235-526-5264",
    "WorkPhone1": "526-235-2462",
    "WorkPhone2": "",
    "FaxPhone": "458-523-5254",
    "Title": "",
    "Email1": "email1@employee.com",
    "Email2": "",
    "Active": "1",
    "Current": "1",
    "PositionID": "0",
    "ManagerID": "0",
    "Level": "2",
    "Address1": "123 Main St.",
    "Address2": "Suite 3501",
    "City": "Fremont",
    "State": "NE",
    "Zip": "45625",
    "Country": "",
    "Position": "",
    "Manager": "",
    "Location": ""
  }
]
```
