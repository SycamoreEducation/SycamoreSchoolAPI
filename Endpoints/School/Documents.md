# School Documents

Returns a list of documents uploaded at the school level

https://app.sycamoreeducation.com/api/v1/School/1002/Documents

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | Limit the number of responses returned from the API  |
| offset | Number of records to skip before starting the response |

### Notes
- Documents that are marked "Internal" in Sycamore will not be included when accessing from a student or family account

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| DocumentID      | The unique identifier of the document         |
| Filename         | The name of the file that was uploaded by the Sycamore user         |
| Comments | Any comments that were added at the time of uploading by the Sycamore user         |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Documents

### Example Response
```json
[
  {
      "DocumentID": "735887",
      "Filename": "GPA_Areas.doc",
      "Comments": ""
  },
  {
      "DocumentID": "733007",
      "Filename": "012615_Newsletter_pdf.pdf",
      "Comments": "Newsletter"
  },
  {
      "DocumentID": "730329",
      "Filename": "baycitylogo.jpg",
      "Comments": ""
  }
]
```
