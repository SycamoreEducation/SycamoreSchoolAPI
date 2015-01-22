# Logout

Removed the users access token from the Sycamore database

https://app.sycamoreeducation.com/api/v1/Logout

## POST

### Notes
- No data has to be sent to this endpoint for it to function correctly
- The access token will be extracted from the POST request automagically
- All 3rd party developers must utilize this endpoint as part of their user auth process, according to section 3.1.1 (Delete at User Request) of the Terms of Use

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Response
```json
{
    "Success": true,
}
```