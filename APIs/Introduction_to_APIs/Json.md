# JSON

What is JSON? 

- JavaScript is a programming language
- JSON was originally created as a way you could hold structured data to be used in a JavaScript
  program. 

  JSON Uses

- It is used for data for all kinds of applications
- JSON has become extremely popular
- It's the most popular way for web APIs to send and receive data

Basic Data Types

- Strings: text enclosed in double quotation marks
- Numbers: integer or decimal, positive, negative or zero
- Booleans: true or false, no quotation marks
- Null: means "nothing", no quotation marks

Arrays

- Arrays are lists
- In square brackets
- Comma-separated
- Can mix data types

Examples:

- [4, 5, -7, 0, 23.1]
- ["red", "green", "blue"]
- [65, "toast", true, 21, null, 100]

Objects

- Objects are JSON's dictionaries
- Dictionaries are enclosed in curly brackets
- the keys and values are separated by a colon
- Each key and value pair are then separated by commas
- Keys and values can be any data type

Examples:

{"red":125, "green":127, "blue":147}

Nested

- Nesting means you've got arrays and objects inside of each other, creating multiple
  layers of collections
- You can put arrays inside of objects, objects inside of arrays, arrays in arrays
  and so on
- Sometimes a JSON file is one big object with lots of other objects and arrays
  inside of that one, top-level object.

Examples:

{
    "forecast": [
    {
        "Monday": {
            "description": "sunny",
            "maxTemp": 22,
            "minTemp": 20,
            "windSpeed": 12,
            "danger": false
        }
    },
    {
        "Tuesday": {
            "description": "windy",
            "maxTemp": 22,
            "minTemp": 20,
            "windSpeed": 40,
            "danger": true
        }
    },
    {
        "Wednesday": null
    }
    ]
}

Document one-level JSON Responses

|Element  |Description              |Type   |Notes|
|---------|-------------------------|-------|-----|
|firstName|First name               |String |     |
|lastName |Last name                |String |     |
|age      |Age in year              |Number |     |
|fullTime |True if working full time|Boolean|Full time is defined as 40 hours per week|

Examples:

The weather forecast for one day

|Element|Description|Type|Notes|
|----|---|---|---|
|date|Data of the forecast |String| View of data YYYY-MM-DD|
|description|What is the weather now|String|State: sunny, overcast, partly cloudy, raining, and snowing|
|maxTemp|High temperature|Number|In degrees Celsius|
|minTemp|Low temperature|Number|In degrees Celsius|
|windSpeed|The speed of the wind |Number|In kilometers per hour|
|danger|The weather was danger or not|Boolean| |

The weather forecast / Represents the weather forecast for multiple days

|Element|Description|Type|Notes|
|---|---|---|---|
|longitud|Longitude coordinates|Number| |
|latitude|Latitude coordinates|Number| |
|forecasts|The description of weather|Array of daily forecast objects| |
|&nbsp; &nbsp; date|Data of the forecast|String|View of data YYYY-MM-DD|
|&nbsp; &nbsp; description|What is the weather now|String|State: sunny, overcast, partly cloudy, raining, and snowing|
|&nbsp; &nbsp; maxTemp|High temperature|Number|In degrees Celsius|
|&nbsp; &nbsp; minTemp|Low temperature|Number|In degrees Celsius|
|&nbsp; &nbsp; windSpeed|The speed of the wind |Number|In kilometers per hour|
|&nbsp; &nbsp; danger|The weather was danger or not|Boolean| |

The creation of meeting / Represents a request for a meeting in a calendar.

|Element|Description|Type|Required|Notes|
|---|---|---|---|---|
|meeting|Top Level|Object|Required| |
|&nbsp; &nbsp; time|The time when the meeting starts|String|Required|View of data YYYY-MM-DD HH-MM in GMT|
|&nbsp; &nbsp; duration|How much time the meeting continues|Number|Required|In minutes|
|&nbsp; &nbsp; description|The name of meeting|String|Required| |
|&nbsp; &nbsp; location|Location of meeting|Number|Optional|The default is an empty string|
|&nbsp; &nbsp; reminder|The time to remind in minutes|Number|Optional|The default is 10 minutes|
|&nbsp; &nbsp; invitees|The list of email participant|Array of string|Optional|The strings should be valid email addresses. The default is an empty array|

