# School Information
Retrieves basic information about a school

## GET

### Endpoint

https://app.sycamoreeducation.com/api/v1/School/:schoolid

###Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

###Parameters
| Fields | Description |
------------------------
Name | The formal name of the school
Address1 |	First address field of the school
Address2 | Second address field of the shool
City |	City the school is located in
State |	State the school is located in
ZIP | ZIP code that the school is located in
Phone | Primary phone number of the school
Color | HEX color that the school has chosen for their menu
Motto |	School motto as specified by the school
WebSite | URL of the official school website
Facebook | URL of the official school Facebook page
Twitter | URL of the official school Twitter page
YouTube | URL of the official school YouTube page
Pinterest | URL of the official school Pinterest page
TimeZone  |	Timezone that the school resides in
WeatherFormat | Indicates which format the school would like to see temperature in (F or C)
Academic | Object containing academic information for the school
> SchoolYearID | The current school year ID
> CurrentQuarter | Current Quarter that the school is in
