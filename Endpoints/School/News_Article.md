# School News Article

Retrieves a single news article from the school

https://app.sycamoreeducation.com/api/v1/School/:schoolid/News/:id

## GET

### Parameters

| Field | Description |
|-------|-------------|
| nohtml | Boolean (1/0) indicating if you want plain text or full formatting in the content |

### Notes
- * denotes optional parameter
- Viewing of this news article is logged for the user
- Anchor tags ( <a> ) will be left in the content despite nohtml requests
- Formatting of the content is up to the school - odd things may occur which are out of the API's control

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Title |	The title of the news article |
| Content |	The text that makes up the news article |
| Author |	First and last name of the user who created the news article |
| Day | The date that the news article was published |
| PhotoURL | Full URL to the primary photo of this news article |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/News/585326

### Example Response
```json
{
    "Title": "Spring Recital ",
    "Content": "Your students have been working hard to prepare for the annual music recital and now the 
time is almost here!  Here are some things you will need to know.

♫  The recital is Sunday, April 2, 2:00-3:30 pm.  Please arrive early enough to get settled 
so we can begin on time.  If you arrive late, please wait at the door until the student who is 
playing has finished before you seat yourself.",
    "Author": "Abigail  Hutson",
    "Day": "Mar 13th, 2014",
    "PhotoURL": "https://app.sycamoreeducation.com/Schools/1002/0/Photos/ComputerCrazy.gif"
}
```