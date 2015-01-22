# User Journals

Retrieves a list of journal entries created and owned by a user

https://app.sycamoreeducation.com/api/v1/User/:UserID/Journals

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | 	The number of journals that will be returned |
| offset | 	Number of records to skip before starting the response |
| preview | 	Boolean value that indicates if a substring of the journal content should be returned with results |

### Notes
- All journals are returned ordered date created in descending order
- The 'limit' paramater's default is 10 and the 'offset' paramater's default is 0

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID  |	Unique identifier of the journal entry |
| Title  |	The title of the journal entry |
| Date 	|The date (YYYY-MM-DD format) that this journal was created |

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/Journals?limit=2

### Example Response
```json
[
    {
        "ID": "19090",
        "Title": "This is a BRAND NEW title",
        "Date": "2014-06-19"
    },
    {
        "ID": "19089",
        "Title": "Saras Birthday",
        "Date": "2014-06-18"
    }
]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Message *  | 	String 	 | The content of the journal | 
| Title 	 | String 	 | The title of the journal article | 
| Date 	 | String 	 | The date in which the journal was created | 

### Notes
- * denotes required field
- If no date is supplied, today's date with be assumed

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Message": "Today I went to the mall. It was boring. I need a more interesting hobby."
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/User/1337/Journals/34234543"
}
```