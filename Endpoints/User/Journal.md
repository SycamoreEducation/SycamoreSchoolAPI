# User Journal Entry

Retrieves the details of a specific journal entry

https://app.sycamoreeducation.com/api/v1/User/:UserID/Journals/:JournalID

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Title 	 | The title of the journal entry | 
| Content  | 	The content of the journal entry | 
| Date  | 	The date (YYYY-MM-DD format) that this journal entry was created on | 

### Example Request

https://app.sycamoreeducation.com/api/v1/User/834534/Journals/19090

### Example Response
```json
{
    "Title": "This is a BRAND NEW title",
    "Content": "I changed the message",
    "Date": "2014-06-19"
}
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Message  | 	String  | 	The content of the journal | 
| Title  | 	String  | 	The title of the journal article | 
| Date  | 	String 	 | The date in which the journal was created | 

### Notes
- List
- of
- notes

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

## DELETE

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request

https://app.sycamoreeducation.com/api/v1/User/87585/Journals/1305287

### Example Response
```json
{
    "Success": 1,
}
```
