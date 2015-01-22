# Class Lunch Orders

Returns the necessary information for submitting classroom lunch orders

https://app.sycamoreeducation.com/api/v1/Class/:ClassID/Cafeteria

## GET

### Parameters

| Field | Description |
|-------|-------------|
| date |  The date (YYYY-MM-DD format) that you'd like to select |

### Notes
- If no date is specified, the current date (UTC) will be used
- The return value "Already" will be set to 1 if there are any lunch orders present for the day

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| Already |	Boolean value indicating whether lunch orders have already been taken for this class today |
| Date |	Date of the lunch records being requests (mm/dd/yyyy format) |
| MealCount | 	A numeric value representing the number of meals are available for selection |
| StudentCount |	Total number of students eligible for lunch in this class |
| Students |	Object of individual students |
| > ID |	Unique ID for that student |
| > Code |	Sycamore's code for that specific student |
| > FirstName |	The student's first name |
| > LastName | 	The student's last name |
| Meals | Object of meals (up to 5) available for selection |
| > MealID | Unique ID number for the given meal |
| > MealName | Title for the meal in question |
| MilkOrders | Object of Student IDs indicating milk orders (if orders have not been submitted) |
| > Count |Number of milks ordered by the student |
| > LTID | 	The Lunch Transaction ID that goes with the milk order |
| MealOrders | 	Object of StudentIDs indicating meal orders (if orders have not be submitted) |
| > MealID | 	Unique ID of the meal that was ordered |
| > Count |	Quantity of the meal ordered |
| > ChargeDate | 	Date that the meal order was charged |
| > OrderDate |	Date that the meal was ordered |
| > LTID | The Lunch Transaction ID that goes with the milk order |

### Example Request

https://app.sycamoreeducation.com/api/v1/Class/58418/Cafeteria

### Example Response
```json
{
    "Already": 0,
    "Date": "05/21/2014",
    "MealCount": 2,
    "StudentCount": 4,
    "Students": [
        {
            "ID": "677887",
            "Code": "AAN1782-2",
            "FirstName": "Jason",
            "LastName": "Aanerud"
        },
        {
            "ID": "387701",
            "Code": "ABE1571-2",
            "FirstName": "Saraç Hailey",
            "LastName": "Abella"
        },
        {
            "ID": "243260",
            "Code": "ART1427-1",
            "FirstName": "Laura",
            "LastName": "Artrip"
        },
        {
            "ID": "435",
            "Code": "BEC1085-4",
            "FirstName": "Esther",
            "LastName": "Beckner"
        }
    ],
    "Meals": [
        {
            "Meal": {
                "MealID": "5198",
                "MealName": "Beef Stroganoff"
            }
        },
        {
            "Meal": {
                "MealID": "8798",
                "MealName": "Chicken Nuggets"
            }
        }
    ]
}
```

## POST

### Parameters

| Field      | Type     | Description |
|------------|----------|-------------|
| Date |	String  |	The date (YYYY-MM-DD format) that lunch is being submitted for |
| Students *  |	Array  |	An array of students with student ID's as the keys |
| > MealID  |	Interger  |	The ID of the meal the student has ordered |
| > MealQuantity  |	Interger  |	The number of meals the student would like to order |
| > MilkQuantity  |	Interger  |	The number of milks the student would like to order |

### Notes
- * denotes required field
- When specifying a different date than the current date, make sure the MealIDs your using are actually available. Submitting meals for day when they are not marked as available will cause unforseen issues.

### Returns

On Success: HTTP/1.1 201 Created

Malformed Request: HTTP/1.1 400 Bad Request

Failed Authentication:  HTTP/1.1 403 Forbidden

### Example Request
```json
{
    "Students": {
         "614085": {
             "MealID": "39436",
            "MealQuantity": "2",
            "MilkQuantity": "3"            
        },
        "267278": {
            "MealID": "39436",
            "MealQuantity": "1",
            "MilkQuantity": "1"                
        }           
    }
}
```

### Example Response
```json
{
    "Success": 1,
    "MealCreated": 2,
    "MilkCreated": 2
}
```