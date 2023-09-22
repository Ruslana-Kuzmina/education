#### Composing Query

1.Queries

Basic query writing:

- creating comments
- SQL query best practices
- using an alias
- sorting and limiting query results

2.Query commenting

SQL comment - plain or natural way to describe a query

How towrite a comment:

--this is a comment

/*
Thia is a comment
Created By: Ruslana Kuzmina
Create Data: mm/dd/yy
Description: this is a structure of a basic query
*/

3.Query composition

```sql
/*
Created By: Ruslanan Kuzmina
Create Data: mm/dd/yy
Description: This query displays all customers: first, last names and email addresses
*/

SELECT
  FirstName,
  LastName,
  Email
FROM
  Customer
```

So I started with the FROM clause and what this does is point me in the direction of where
the data is. So FROM Customer effectively says, go to the Customer table.

And by putting SELECT up here and specifying the columns, it's effectively saying, well
now that I'm at the Customer table, I'd like to see the first name, last name and email
address displayed.

5.Colunm custom names

**Aliases** allow us to rename our columns to names that are more appropriate to
the business.

```sql
SELECT
  FirstName AS [Customer First Name],
  LastName AS 'Customer Last Name',
  Email AS EMAIL
```

6.Sorting query results

First step is to include a brand new clause which comes after the FROM clause called
the ORDER BY clause. By placing that clause there, and then specifying the column,
we now want to order by which in this case is the last name, 

We can go in one of two different ways:

- We can either sort ascending which is A to Z
- We can sort descending order

The ascending order sort is actually the default sort in SQL.

```sql
FROM 
  Customer
ORDER BY
  FirstName ASC,
  LastName DESC
```

7.Limiting query results

```sql
ORDER BY
  FirstName ASC,
  LastName DESC
LIMIT 10
```

LIMIT clause -  help to chose the 10 lines

Tests

4.Composing queries

- The Street field contains Hickory, Elm, and Sycamore. Which occurs first if sorted
  in descending order?

  - [x] Sycamore
        Descending order puts the end of the alphabet first.
  - [ ] Hickory
  - [ ] Elm

- What is wrong with the following query?

```sql
SELECT
    Street
    ZIP
FROM
    Customers
```

  - [ ] There should only be one item after SELECT.
  - [ ] FROM and SELECT are in the wrong order.
  - [x] Items after SELECT should be separated by commas.
        Line breaks are optional, but commas are essential.
  - [ ] Items after SELECT should be enclosed in parentheses.