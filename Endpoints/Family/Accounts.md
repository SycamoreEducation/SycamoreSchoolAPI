# Family Accounts

Retrieves a list of accounts and their balances for a family

https://app.sycamoreeducation.com/api/v1/Family/:FamilyID/Accounts

## GET

### Notes
- Two accounts are hardcoded within the system (childcare and cafeteria). The rest are dynamically created by each school.

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID |	Unique identifier of the account ("cafeteria" or "childcare" for hardcoded results) |
| Name | 	The name of the account |
| Amount | 	The current balance in that account for the family |

### Example Request

https://app.sycamoreeducation.com/api/v1/Family/647150/Accounts

### Example Response
```json
[
    {
        "ID": "3478",
        "Name": "Tuition 2013-14",
        "Amount": "500.00"
    },
    {
        "ID": "cafeteria",
        "Name": "Cafeteria",
        "Amount": "-2.73"
    },
    {
        "ID": "childcare",
        "Name": "Childcare ",
        "Amount": "15.00"
    }
]
```