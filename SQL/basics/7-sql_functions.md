# SQL Functions

## 1.Calculating with functions

How to use something called functions to simplify your calculations and eliminate
the need for you to do any manual counting, functions are one of the most powerful
features of SQL.
Some of the most commonly used functions in SQL including:

- aggregate
- string
- date and time functions

## 2.String, date, and aggregate function types

Now, when I type in the keyword or the function UPPER, then open parenthesis, we
do see this popup in front of us which is telling us a little bit more about the
UPPER function and what it expects.That's very helpful in determining what arguments
the function takes and what the function actually does.

## 3.Connecting strings

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Create a Mailing List of US Customers?
*/

SELECT
  FirstName,
  LastName,
  Address,
  FirstName ||' '|| LastName ||' '|| Address ||', '|| City ||' '|| State ||' '|| PastalCode AS [Mailing Address]
FROM 
  Customer
Where
  Country='USA'
```

Let's see how we could use our SQL string functions to build this field. 

Now, when it comes to joining separate fields, this is referred to as **concatenating**
them in SQL. We use the double pipe operator in SQLite. 

Concatenate - linking things together in a chain or series, объединить строки


I'm going to make a quick single line comment just to demonstrate that the double
pipe || is just simply the pipe symbol on your keyboard two times. 
|| - join two separate fields together FirstName and LastName

We don't have it looking very readable without a space between the first and the
last name. We would need to now put a pair of single quotes with a space in between.

## 4.Separating text

Truncate - to shorten or reduce - сократить 

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Create a Mailing List of US Customers?
*/

SELECT
  FirstName,
  LastName,
  Address,
  FirstName ||' '|| LastName ||' '|| Address ||', '|| City ||' '|| State ||' '|| PastalCode AS [Mailing Address],
  LENGTH(postalcode),
  substr(posatalcode,1,5) AS [5 Digital PostalCode]
FROM 
  Customer
Where
  Country='USA'
```

SUBSTR()Function - used to truncate strings of text

I'm going to go into a new line here and start typing, S, U, B, S, T, R and open
parenthesis. And this sub string function actually removes the extra US postal codes
from this particular field. To do this, we're going to say first, the field that
we want to manipulate or change which is the postal code. Then we specify the first
digit that we want to start the removal, which is from digit number one or position
number one. And then we want to keep the five postal code digits that will allow
our mailing address or letters. We want to keep the five digits or the five zip codes
that are going to allow our packages or postcards to get to their intended recipients.
So let's indicate that we want to keep five digits by putting a comma in five and
then we're going to close our sub string function.

The updated mailing list with a nicely updated and cleaner five digit postal code.

## 5.UPPER and LOWER string functions

UPPER()Function - converts a string of text to uppercase
LOWER()Function - converts a string of text to all lowercase

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Create a Mailing List of US Customers?
*/

SELECT
  FirstName,
  LastName,
  Address,
  FirstName ||' '|| LastName ||' '|| Address ||', '|| City ||' '|| State ||' '|| PastalCode AS [Mailing Address],
  LENGTH(postalcode),
  substr(posatalcode,1,5) AS [5 Digital PostalCode],
  upper(firstname) AS [First Name All caps],
  lower(lastname) AS [Last Name All Lower]
FROM 
  Customer
Where
  Country='USA'
```

## 6.Date functions

**Date functions** allow the manipulation of data that's stored in various date
and time formats. 

We are stored in both date and time. And that is year, month, day followed by hour,
minute, and second.

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Calculate the ages of all employees
*/

SELECT
  FirstName,
  LastName,
  BirthDate,
  strftime('%Y-%m-%d', Birthdate) AS [Birthdate No Timecode],
  strftime('%Y-%m-%d', 'now') - strftime('%Y-%m-%d', Birthdate) AS Age
FROM
  Employee
```

To perform such a calculation, we can employ a new date function which is called
the **strftime**. The strftime function converts date and time strings into another
format.

## 7.Aggregate functions

AGGREGATE()Function - turn a range of numbers into a single point of data based on
a variety of mathematical operations

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Aggregate Functions | What are our all time global sales?
*/

SELECT
  SUM(Total) AS [Total Sales],
  AVG(Total) AS [Average Sales],
  MAX(Total) AS [Maximum Sales],
  MIN(Total) AS [Minimum Sales],
  COUNT(*) AS [SALES COUNT]
FROM
  Invoice
```

Count - we can count every single row within our invoice table.

## 8.Nesting functions

A nested function is a function that's contained within another function.

An appropriate function here is a new function called the **round function**, and
what the round function does is that it returns a floating point value rounded to
the number of digits that you specify. Now I'm going to say a comma at this point.
And then I'm going to apply how many digits do I want to round this value to? Then
I'm going to close off this function.

And this round function expects two parameters which is the value to be rounded
which is our average value now currently with many digits after the decimal point.
And now we are going to limit it to just two decimal places with the use of this
second argument in our round function.

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Aggregate Functions | What are our all time global sales?
*/

SELECT
  SUM(Total) AS [Total Sales],
  round(AVG(Total),2) AS [Average Sales],
  MAX(Total) AS [Maximum Sales],
  MIN(Total) AS [Minimum Sales],
  COUNT(*) AS [SALES COUNT]
FROM
  Invoice
```

Tests:

- Which code produces FROG from ParkFrog in the field text0?

    - [ ] UPPER(substr(text0,4,4))
    - [ ] UPPER(substr(text0,5,1))
    - [x] UPPER(substr(text0,5,4))
          The user can nest multiple functions.
    - [ ] LOWER(substr(text0,5,4))

- What are some valid string functions?

    - [x] UPPER(), TRIM(), and LOWER()
          Yes, these are all valid string functions.
    - [ ] COUNT(), SUM(), and AVG()
    - [ ] TIME(), STRFTIME(), and TRIM()
    - [ ] DATE(), MIN(), and MAX()

- How would you calculate the range of data values in the field Total?

     - [x] Subtract MIN(Total) from MAX(Total).
           The difference between the maximum and minimum values is the range.
     - [ ] Divide SUM(Total) by AVG(Total).
     - [ ] Add COUNT(Total) to MIN(Total).