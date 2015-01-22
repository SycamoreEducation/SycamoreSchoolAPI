# School Cafeteria Menu

Retrieves a list of school defined cafeteria lunches

https://app.sycamoreeducation.com/api/v1.0/School/1002/Cafeteria

## GET

### Parameters

| Field | Description |
|-------|-------------|
| limit | The number of days that will be returned |
| start | The date (YYYY-MM-DD) used as the starting point for selecting records |
| end | The date (YYYY-MM-DD) used as the ending point for selecting records |

### Notes
- If no limit is specified, only the next 5 days will be returned
- If no start date is specified, the current date will be used
- If no end date is specified, the limit parameter will be used to limit the records returned
- If no meals are select for a calendar day, that day will be excluded from the returning data

### Returns

On Success: HTTP/1.1 200 OK

Nothing To Return: HTTP/1.1 204 No Content

Failed Authentication:  HTTP/1.1 403 Forbidden

| Field      | Description |
|------------|-------------|
| MM/DD/YYYY | An object named after the day that is being returned |
| > MealName | The name specified for the meal being served |
| > MealDesc | The description given for the meal |

### Example Request

https://app.sycamoreeducation.com/api/v1/School/1002/Cafeteria?limit=2

### Example Response
```json
{
    "05/09/2014": [
        {
            "MealName": "Big Breakfast",
            "MealDesc": "SausagernMuffinrn"
        },
        {
            "MealName": "Big Breakfast",
            "MealDesc": "SausagernMuffinrn"
        },
        {
            "MealName": "Beef Stroganoff",
            "MealDesc": "Mashed PotatoesrnGreen BeansrnRoll & ButterrnApple Crisp"
        }
    ],
    "05/12/2014": [
        {
            "MealName": "Big Breakfast",
            "MealDesc": "SausagernMuffinrn"
        },
        {
            "MealName": "Chicken Fried Steak",
            "MealDesc": "Mashed PotatoesrnCornrnSaladrnSugar Cookie"
        },
        {
            "MealName": "Cheese Pizza",
            "MealDesc": "side saladrngarlic breadrnchoice of fruitrnmilk or juice"
        }
    ]
}
```