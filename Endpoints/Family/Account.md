# Family Account

Retrieves a list of transactions for an account that affect the specified family

https://app.sycamoreeducation.com/api/v1/Family/:FamilyID/Accounts/:AccountID

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | 	Limit the number of responses returned from the API|
| offset |	Number of records to skip before starting the response|

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID | 	Unique identifier for this transaction |
| Amount | 	Dollar amount that a transaction was for|
| Comments | 	Any textual comments that were added when the transaction was created|
| Date |	The date that the transaction was created|

### Example Request

https://app.sycamoreeducation.com/api/v1/Family/64745/Accounts/4533

### Example Response
```json
[
    {
        "ID": "3045188",
        "Amount": "500.00",
        "Comments": "Tuition - High School (12 Payments)",
        "Date": "May 22nd, 2014"
    }
]
```