# School Information

Retrieves basic information about a school

https://app.sycamoreeducation.com/api/v1/School/:schoolid

## GET

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Parameters

| Fields | Description |
|----------------------|
| Name | The formal name of the school
| Address1 |	First address field of the school
| Address2 | Second address field of the shool
| City |	City the school is located in
| State |	State the school is located in
| ZIP | ZIP code that the school is located in
| Phone | Primary phone number of the school
| Color | HEX color that the school has chosen for their menu
| Motto |	School motto as specified by the school
| WebSite | URL of the official school website
| Facebook | URL of the official school Facebook page
| Twitter | URL of the official school Twitter page
| YouTube | URL of the official school YouTube page
| Pinterest | URL of the official school Pinterest page
| TimeZone  |	Timezone that the school resides in
| WeatherFormat | Indicates which format the school would like to see temperature in (F or C)
| Academic | Object containing academic information for the school
| > SchoolYearID | The current school year ID
| > CurrentQuarter | Current Quarter that the school is in

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002

### Example Response
```json
{
    "Name": "Tri-County School",
    "Address1": "1234  Main St",
    "Address2": "",
    "City": "Dodge City",
    "State": "NE",
    "ZIP": "68341",
    "Phone": "(555) 555-5557",
    "Color": "720000",
    "Motto": "Home of the Fighting Bulldogs",
    "WebSite": "http://dev.sycamoreeducation.com",
    "Facebook": "www.facebook.com/sycamoreeducation",
    "Twitter": "www.twitter.com/sycamoreedu",
    "YouTube": "www.youtube.com/sycamoreleaf",
    "Pinterest": "www.pintereset.com",
    "TimeZone": "America/Chicago",
    "WeatherFormat": "F",
    "Academic": {
        "SchoolYearID": "208313",
        "CurrentQuarter": "3"
    }
}
```
