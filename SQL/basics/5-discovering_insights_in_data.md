# 5. Discovering Insights in Data

## 1. Types of SQL operators

SQL tools allow us to narrow down results.

Operator types:

- Arithmetic
  - Add +
  - Subtract -
  - Multiply *
  - Divide /
  - Modulo %
- Comparison
  - Equal to =
  - Not equal to <>
  - Greater than >
  - Less than <
  - Greater than or equal to >=
  - Less than ot equal to <=
- Logical
  - AND
  - OR
  - IN
  - LIKE
  - BETWEEN

## 2. Filter and analyze numeric data

The WHERE clause is used to filter records.

It is used to extract only those records that fulfill a specified condition.

SELECT column1, column2, ...
FROM table_name
WHERE condition

```sql
/*
How many customers purchased two songs at 0.99$ each?
*/

/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: Customers who purchased two songs at 0.99$ each
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  total=1.98
ORDER BY
  InvoiceDate
```

Well, with what we've learned thus far, we can select all of the records from the invoice
table, then sort by the total column, and simply manually count all of the records that
are $1.98. 

The WHERE clause comes after the FROM and we're going to specify that we want to see
records where the total is equal to $1.98. We can also include our ORDER BY, which
comes after the WHERE clause, and we want to ORDER BY the InvoiceDate. 

## 3. BETWEEN and IN operators

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices exist between 1.98$ and 5$.
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  total BETWEEN 1.98 AND 5
ORDER BY
 InvoiceDate
```

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices do we have that are exactly 1.98$ or 3.96$?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  total IN (1.98, 3.96)
ORDER BY
 InvoiceDate
```

## 4. Filter and analyze text data

We've used the FILTER clause with numeric data. Now, let's use operators to return
specific text.

When it comes to text, we must include single quotes around the text criteria that
we are searching for.

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices were billed to Brussels?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  BillingCity='Brussels'
ORDER BY
 InvoiceDate
```

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices were billed to Brussels, Orlando or Paris?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  BillingCity IN ('Brussels', 'Orlando', 'Paris')
ORDER BY
 InvoiceDate
```

## 5. Search records without an exact

We've been using the EQUAL operator to search for exact values.

LIKE operator searches for partial or incorrect values.

A wildcard character is used to substitute one or more characters in a string.

Wildcard characters are used with the LIKE operator. The LIKE operator is used in
a WHERE clause to search for a specified pattern in a column.

LIKE Operator	                  Description
WHERE CustomerName LIKE 'a%'    Finds any values that starts with "a"
WHERE CustomerName LIKE '%a'    Finds any values that ends with "a"
WHERE CustomerName LIKE '%or%'  Finds any values that have "or" in any position
WHERE CustomerName LIKE '_r%'   Finds any values that have "r" in the second position
WHERE CustomerName LIKE 'a__%'  Finds any values that starts with "a" and are at least
                                3 characters in length
WHERE ContactName LIKE 'a%o'    Finds any values that starts with "a" and ends with "o"

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices were billed in cities that start with B?
*/

--$ I don't care what comes next

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  BillingCity LIKE 'B%'
ORDER BY
 InvoiceDate
```

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices were billed in cities that have a B anywhere in its name?
*/

--% I don't care

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  BillingCity LIKE '%B%'
ORDER BY
  InvoiceDate
```

## 6. Filter and analyze using dates

So far, we've analyzed NUMERIC and TEXT data. Now, we analyze DATE data.

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices were billed on 2010-05-22 00:00:00?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  InvoiceDate='2010-05-22 00:00:00'
ORDER BY
  InvoiceDate
```

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: How many invoices were billed on 2010-05-22 00:00:00?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  date(InvoiceDate)='2010-05-22'
ORDER BY
  InvoiceDate
```

The result is the same and don't bother about including the time (00:00:00).

## 7.Filter records based on more than one condition

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: Get all invoices were billed after 2010-05-22 and have a total of less
than 3$?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  date(InvoiceDate)>'2010-05-22' AND total<3.00
ORDER BY
  InvoiceDate
```

## 8.Logical operator OR

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: Get all invoices who's billing city is starts with P or starts with D?
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
  BillingCity LIKE 'P%' OR BillingCity LIKE 'D%'
ORDER BY
  InvoiceDate
```

## 9.Brackets and order

```sql
/*
Created BY: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: Get all invoices that are greater than 1.98 from any cities whose name
start with P or starts with D?

PEMDAS: Parenthesis, Exponents, Multiplication/Division, Addition/Subtraction
BEMDAS: Braskets, Exponents, Multiplication/Division, Addition/Subtraction
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total
FROM
  Invoice
WHERE
 total>1.98 AND (BillingCity LIKE 'P%' OR BillingCity LIKE 'D%')
ORDER BY
  InvoiceDate
```

What this does is that it directs SQL to say, "First, bring us all of the cities
that satisfy this criteria." That is, all of the cities that start with P or start
with D. Once we have satisfied this criteria from this subset, then give me all of
the invoice totals that are greater than $1.98. 

PEMDAS is acronym used to remember the order of operations: parenthesis, exponents,
multiplication, and division, addition, and subtraction

PEMDAS if you're in the European part of the world, it's referred to as this, or
BEMDAS if you're in the US. 

The only difference with BEMDAS is we've replaced parenthesis with brackets. 

This is a very important concept when it comes to the order of operation. When we
have multiple criteria that's being asked for in our request, we must consider
the order in which it is going to be executed. And by specifying our brackets around
the area that we want to execute first, we employ the PEMDAS or the BEMDAS rule and
we get the correct result.

## 10.IF THEN logic with CASE

```sql
/*
WSDA Music Sales Goal:
They want as many customers as possible to spend between $7.00 and $15.00

Sales Categories:

Baseline Purchase -  between $0.99 and $1.99
Low Purchase - between $2.00 and $6.99
Target Purchase - between $7.00 and $15.00
Top Performer - above $15.00
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total,
  CASE
  WHEN total<2.00 THEN 'Baseline Purshase'
  WHEN total BETWEEN 2.00 AND 6.99 THEN 'Low Purchase'
  WHEN total BETWEEN 7.00 AND 15.00 THEN 'Target Purchase'
  ELSE 'Top Performer'
  END AS PurchaseType
FROM
  Invoice
ORDER BY
  BillingCity
```

```sql
/*
WSDA Music Sales Goal:
They want as many customers as possible to spend between $7.00 and $15.00

Sales Categories:

Baseline Purchase -  between $0.99 and $1.99
Low Purchase - between $2.00 and $6.99
Target Purchase - between $7.00 and $15.00
Top Performer - above $15.00
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity,
  total,
  CASE
  WHEN total<2.00 THEN 'Baseline Purshase'
  WHEN total BETWEEN 2.00 AND 6.99 THEN 'Low Purchase'
  WHEN total BETWEEN 7.00 AND 15.00 THEN 'Target Purchase'
  ELSE 'Top Performer'
  END AS PurchaseType
FROM
  Invoice
WHERE
  PurshaseType='Top Performer'
ORDER BY
  BillingCity
```

Now, we would also like to include the CASE statement, which actually allows us
to create a new temporary field in our database that serves as a label for the data
based on user-specified conditions.

Test:

- How would you correctly select a record with a Day entry before January 10, 2016,
  and an Amount value more than $1000?

  - [x] WHERE
        DATE(Day) < '2016-01-10' AND Amount > 1000
        Using the "DATE" function makes this clause more robust.
  - [ ] WHERE
        Day = '2016-01-10' AND Amount = 1000
  - [ ] WHERE
        Day < '10-1-2016' AND Amount > 1000
  - [ ] WHERE
        DATE(Day) > '2016-01-10' AND Amount < 1000

- Which word starts a clause to filter results based on a condition?

  - [ ] WHICH
  - [x] WHERE
        "WHERE" introduces a condition typically involving fields and operators.
  - [ ] FROM
  - [ ] AS

- What is the purpose of the ELSE phrase following IF-THEN?

  - [x] It defines what to do if none of the explicit IF conditions are met.
        The object of "ELSE" specifies the catchall outcome.
  - [ ] It introduces a list of conditions defining various categories.
  - [ ] It defines the category name.
  - [ ] It terminates the CASE clause.

- Which WHERE clause is correct?

  - [ ] WHERE
        Street = [Poplar]
  - [ ] WHERE
        Street IN "Poplar"
  - [x] WHERE
        Street = 'Poplar'
        Use single quotes ['] to delimit text.
  - [ ] WHERE
        Street IS [Poplar]