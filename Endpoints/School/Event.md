# School Calendar Event

Retrieves the details of a single calendar event

https://app.sycamoreeducation.com/api/v1/School/:schoolid/Calendar/:id

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Title | 	The title of the calendar event | 
| Notes | 	Any notes specified for the event| 
| Duration | 	How long the event is set to last (HH:MM)| 
| Location | The location where the event is set to take place| 
| Day | 	The date that the event is set to take place| 
| Start|  	The start time (24h format) of the event| 
| AllDay | 	Boolean value indicating whether the event is a full day event (Start field may be disregarded)| 
| Managed | 	Boolean value indicating if the event is being managed with the Event Mgr feature| 
| Volunteer | 	Boolean value indiciating if the event is being coordinated with the Volunteer Mgr feature| 
| Public | 	Boolean value indicating if this event is marked as a 'Public' event| 

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Calendar/2032575

### Example Response
```json
{
    "Title": "Mobile App View",
    "Notes": "This is a test note for this event",
    "Duration": "01:00",
    "Location": "Cafeteria from text field - not Facility menu",
    "Day": "12-17-2013",
    "Start": "12:09",
    "AllDay": "1",
    "Volunteer": "0",
    "Managed": "0",
    "Public": "0"
}
```