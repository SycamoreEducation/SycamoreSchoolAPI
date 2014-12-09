# Family Details

Retrieves details of a specific family

https://app.sycamoreeducation.com/api/v1/Family/:FamilyID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field | Description |
| ----------------------|
| ExtID | School given identifier for the family |
| Code | The Sycamore given family code |
| Name | General family name | 
| FormalName |Family name with titles |
| MessagerID | The ID of the student of the family who is designated as the messanger
| Memo | The text of the 'memo' field of the family profile
| SecretWord | The text of the 'secret word' field of the family profile
| MailingAddress1 |	First line of mailing address
| MailingAddress2 | Second line of mailing address
| MailingCity | City of mailing address
| MailingState | State of mailing address
| MailingZIP | ZIP of mailing address
| MailingCountry | Country of mailing address
| HomePhone | Given family home phone number
| BillingName | Name to use when addressing family with billing information
| BillingAddress1 | First line of billing address
| BillingAddress2 | Second line of mailing address
| BillingCity | City of billing address
| BillingState | State of billing address
| BillingZIP | ZIP of billing address
| BillingCountry | Country of billing address
| BillingPhone | Given family billing phone number

### Example Request

https://app.sycamoreeducation.com/api/v1/Family/647150

### Example Response
```json
{
    "ExtID": "1337",
    "Code": "TOM3444",
    "Name": "Tomson, Tony & Diane",
    "FormalName": "Dr. & Mrs. Tony Tomson",
    "MessagerID": "614085",
    "Memo": "He smells funny",
    "SecretWord": "Riverrunsthrough",
    "MailingAddress1": "122 South Diverson Ave",
    "MailingAddress2": "",
    "MailingCity": "Riverton",
    "MailingState": "NJ",
    "MailingZIP": "45433",
    "MailingCountry": "",
    "HomePhone": "5555551515",
    "BillingName": "",
    "BillingAddress1": "",
    "BillingAddress2": "",
    "BillingCity": "",
    "BillingState": "",
    "BillingZIP": "",
    "BillingCountry": "",
    "BillingPhone": ""
}
```
