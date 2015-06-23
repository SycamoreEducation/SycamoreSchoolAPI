# School Document

Returns the details about a specific school-level document

https://app.sycamoreeducation.com/api/v1/School/1002/Documents/12345

## GET

### Notes
- A absolute URL will be returned where the document can be downloaded 

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Filename     | The name of the file at the time of uploading         |
| Destination         | A absolute URL where this document can be downloaded/viewed         |
| Comments | Any comments made on the document by the user who uploaded it         |
| Size | The size (in bytes) of the document |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Documents/123445

### Example Response
```json
{
  "Filename": "creativecollective-square.png",
  "Destination": "Downloads/1002/creativecollective-square.png",
  "Comments": "",
  "Size": "196828"
}
```
