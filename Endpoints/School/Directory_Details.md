# School Directory (Family)

Retrieves a list of families and their basic contact information

https://app.sycamoreeducation.com/api/v1/School/:schoolid/Directory/:id

## GET

### Parameters

| Field | Description |
|-------|-------------|
| uspf | US Phone Format. Returns pre-formatted phone number (555) 123-4567 |

### Notes
- Schools may turn off access to the directory
- Families must be enabled to appear in the directory
- Individual families may opt out of sharing information (address, phone #, email) through the directory

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Name | Common name for the family |
| Address1  | 	First line of family address |
| Address2 |  Second line of family address |
| City  | 	City where this family resides |
| State  | 	State the family resides in |
| ZIP 	 | ZIP code of family address |
| HomePhone  | 	The home phone number for the family |
| Parents  | 	An object for each individual contact who is marked as primary parent for that family |
| > FirstName  | 	The first name of the contact |
| > LastName  | 	The last name of the contact |
| > Relationship  | 	How this contact is related to their students |
| > HomePhone  | 	The home phone number for this contact |
| > Email 	 | The email address for this contact |
| > Address1  | 	First line of contact address |
| > Address2  | 	Second line of contact address |
| > City 	 | City where this contact resides |
| > State  | 	State the contact resides in |
| > ZIP 	 | ZIP code of the contact address |
| Students  | 	An object for each student associated with this family |
| > FirstName |  	First name for the student |
| > LastName  | 	Last name for the student |
| > Grade 	 | Current grade for this student |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Directory/239

### Example Response
```json
{
    "Name": "Sampson, Glenn",
    "Address1": "76 Burgundy Lane",
    "Address2": "",
    "City": "Joplin",
    "State": "MO",
    "ZIP": "",
    "HomePhone": "", 
    "Parents": [
        {
            "FirstName": "Glenn",
            "LastName": "Sampson",
            "Relationship": "Father",
            "HomePhone": "(402) 555-55555",
            "Email": "joe@mail.com",
            "Address1": "123 Main St",
            "Address2": "",
            "City": "Anytown",
            "State": "AK",
            "ZIP": "55455"
        }
    ],
    "Students": [
        {
            "FirstName": "Brigette",
            "LastName": "Sampson",
            "Grade": "4th"
        },
        {
            "FirstName": "Priscilla",
            "LastName": "Sampson",
            "Grade": "6th"
        },
        {
            "FirstName": "Paris",
            "LastName": "Sampson",
            "Grade": "Freshman"
        }
    ]
}
```