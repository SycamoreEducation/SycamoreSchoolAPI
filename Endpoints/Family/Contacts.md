# Family Contacts

Retrieves a list of contacts that are associated with a family

https://app.sycamoreeducation.com/api/v1/Family/:FamilyID/Contacts

## GET

### Parameters

| Field | Description |
|-------|-------------|
| primary | Boolean (1/0) to filter all contacts from just primary contacts |

### Notes
- If primary is set to 0 or not set, all contacts for a family will be returned

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
|ID 	| Unique identifier of the contact| 
| FirstName | 	First name of the contact| 
| LastName | 	Last name of the contact| 
| WorkPhone | 	Work phone number of the contact| 
| HomePhone  |    Home phone number of the contact| 
| CellPhone | 	Cell phone number of the contact| 
| Email 	| Email address of the contact| 
| Relation | 	The relation of this contact to the family unit| 
| PrimaryParent | 	Boolean value to designate if this contact is considered a 'primary contact'| 
| Pickup | 	Boolean value to indicate if this contact is able to pickup the students of this family from the school| 
| Emergency | 	Boolean value to indicate if this contact is considered an 'emergency' contact| 

### Example Request

https://app.sycamoreeducation.com/api/v1/Family/647150/Contacts

### Example Response
```json
[
    {
        "ID": "773022",
        "FirstName": "Joe",
        "LastName": "Rogan",
        "WorkPhone": "",
        "HomePhone": "(555) 545-5454",
        "CellPhone": "(555) 555-5555",
        "Email": "joe@fearfactor.com",
        "Relation": "Father",
        "PrimaryParent": "1",
        "Pickup": "1",
        "Emergency": "1"
    },
    {
        "ID": "773023",
        "FirstName": "Lisa",
        "LastName": "Rogan",
        "WorkPhone": "",
        "HomePhone": "555 555 3333",
        "CellPhone": "",
        "Email": "lisa@coxbroadband.com",
        "Relation": "Mother",
        "PrimaryParent": "1",
        "Pickup": "1",
        "Emergency": "1"
    },
    {
        "ID": "1088519",
        "FirstName": "Diane",
        "LastName": "Missel",
        "WorkPhone": "",
        "HomePhone": "402 555 5555",
        "CellPhone": "",
        "Email": "",
        "Relation": "Grandmother",
        "PrimaryParent": "0",
        "Pickup": "1",
        "Emergency": "1"
    }
]
```