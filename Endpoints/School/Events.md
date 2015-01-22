# School Calendar Events

Retrieves a list of calendar events for the school

https://app.sycamoreeducation.com/api/v1.0/School/:schoolid/Calendar

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | Limit the number of responses returned from the API |
| offset | Number of records to skip before starting the response |
| start | The date (YYYY-MM-DD) used as the starting point for selecting records |
| end | The date (YYYY-MM-DD) used as the ending point for selecting records |

### Notes
- Will not grab events that are marked 'Internal' within the system
- If no limit is set, the next 10 calendar events will be supplied

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| ID | 	The unique identifier for the specific calendar event| 
| Title | 	The title of the calendar event| 
| Day | 	The date that this event will take place on| 
| Timestamp | The Unix timestamp of the Day field| 

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Calendar?limit=3

### Example Response
```json
[
    {
        "ID": "79",
        "Title": "Back",
        "Day": "01/03/73",
        "Timestamp": "94867200"
    },
    {
        "ID": "1292876",
        "Title": "Pizza Party",
        "Day": "02/27/98",
        "Timestamp": "888537600"
    },
    {
        "ID": "62",
        "Title": "Annual Book Sale",
        "Day": "09/13/00",
        "Timestamp": "968803200"
    }

]
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Title * | 	String|  	The title of the calendar event| 
| ShortTitle | 	String | 	The shorter title (20 characters) that will be displayed on the calendar| 
| Date | 	Date (YYYY-MM-DD) | 	The date that this calendar event is taking place. Default: Current date| 
| ClassID | 	Interger | 	The ID of the class this event is assigned to. Default: 0| 
| Internal|  	Boolean | 	Indicating if this event should only be seen by employees. Default: 0| 
| AllDay | 	Boolean | 	Indicating if this event should be 'untimed' and run all day long. Default: 0| 
| Time | 	String | 	The time (HH:MM) in 24-hour format that the event is taking place.| 
| Public | 	Boolean | 	Should this news article be considered public. Default: 0| 
| Duration | 	String | 	The duration (HH:MM) of the event.| 
| Location | 	String | 	Where this event is taking place| 
| Notes | 	Text 	| Any additional notes about this particular event| 
| Managed | 	Boolean | 	Indicating if this event is being used by the Event Mgr. Default: 0| 
| Volunteer | 	Boolean | 	Indicating if this event is being used by the Volunteer Mgr. Default: 0| 

### Notes
- * denotes required field

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Title": "Test Event",
    "ShortTitle": "API",
    "Date": "2014-06-19",
    "AllDay": "0",
    "Time": "13:00",
    "Duration": "01:15",
    "Location": "Worldwide",
    "Notes": "You are theBomb.com",
    "Managed": "0",
    "Volunteer": "0",
    "Public": "1",
    "Internal": "1"
}
```

### Example Response
```json
{
    "Success": 1,
    "Location": "https://app.sycamoreeducation.com/api/v1/School/1002/Calendar/3305418"
}
```