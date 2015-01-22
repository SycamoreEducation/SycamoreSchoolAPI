# School News Articles

Retrieves a list of school news articles

https://app.sycamoreeducation.com/api/v1/School/:schoolid/News

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit   | Limit the number of responses returned from the API |
| offset  | Number of records to skip before starting the response|
| start  | The date (YYYY-MM-DD) used as the starting point for selecting records |
| end  | The date (YYYY-MM-DD) used as the ending point for selecting records |
| preview   |	Returns the first 300 characters of a news article |
|classid   |	Returns news articles that are associated with this classid |
|nohtml   |	Indicates if you want plain text or full formatting with the content |
|breaktype  | Indicate if you want unix newline characters or HTML <br> tags. Options are: nl or br | 


### Notes
- Will not return news articles marked 'Internal'
- If no ClassID is given, all news articles not associated with a class with be returned
- Anchor tags ( <a> ) will be left in content regardless of nohtml paramater preference

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID | 	Unique ID field for the record returned | 
| Day |	The date that the news article was created | 
| UnixTime | 	Unix Timestamp of the 'Day' return field | 
| Title | The title of the news article | 
| Content * | 	A 300 character snippet of the news artlce content | 

### Notes
- * Return fields optional and specified by request

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/News?limit=3

### Example Response
```json
[
    {
	"ID": "585326",
	"Day": "12/09/13",
	"UnixTime": "1386604800",
	"Title": "Gear Up for Winter"
    },
    {
	"ID": "577472",
	"Day": "11/20/13",
	"UnixTime": "1384966800",
	"Title": "Inclement Weather"
    },
    {
	"ID": "525171",
	"Day": "08/27/13",
	"UnixTime": "1377626400",
	"Title": "Backpack Back Pain"
    }
]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Title * | 	String | 	The title of the news article| 
| Content * | 	Text | 	The content of the news article| 
| Date | 	Date (YYYY-MM-DD)|  	The date that this news article was published. Default: Current date| 
| ClassID | 	Interger | 	The ID of the class this news article is assigned to. Default: 0| 
| Internal | 	Boolean | 	Indicating if this news article should only be seen by employees. Default: 0| 
| Comments | 	Boolean | 	Should this article allow comments. Default: 0| 
| Notify | 	Boolean | 	Does the author want to be notified of comments on this article. Default: 0| 
| Public | 	Boolean | 	Should this news article be considered public. Default: 0| 

### Notes
- * denotes required field

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Title": "API",
    "Content": "This news article was created via the API.",
    "Internal": "1",
    "Public": "1",
    "Comments": "0",
    "Date": "2014-06-19",
    "Notify": "1"
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/School/1002/News/433425"
}
```