# The Basics of Database Structures

- Relational Database theory

Data is the plural of the word datum, and a datum is defined as a piece of information.
So data are pieces of information like your last social media post, whether that's text,
images, or video, or the last phrase you search for on Google. 

Second, a database. It's simply a collection of data. That data can be organized in many
different ways, but it's usually organized in tables. 

Now, what are tables? In the world of SQL, tables are made up of rows and columns. Rows
run left to right and columns up and down, think Excel spreadsheet. Each row represents
a single piece of data called a **record**. Each column represents a specific attribute
of that data, such as name or address. In order to get the data, take a look at it, and
analyze it, we use a special language called **SQL**, short for Structured Query Language.
SQL includes many different commands or keywords. One of the most common is SELECT. 

SELECT statement
- common SQL command
- specifies table columns

- The SDLite database engine

The software system that's used to compose SQL statements is called a **Relational**
**Database Management System or RDBMS** for short. 

So an RDBMS, though there are many different varieties, the singular function is to
allow us an area to compose SQL statements. 

The SELECT clause   |
The FROM clause     |    SQL Statement
The ORDER BY clause |

SELECT
    InvoiceData     |
    BillingAdress   |    Fields
    BillingSity     |
    Total           |

FROM
    invoices        |    Table

ORDER BY
    Total;

### The SQLite Database Environment

1.How to access the DB Browser for SQLite software

There are a few reasons for choosing DB Browser, but some of the main reasons are:

- SQLite is a free
- SQLite open source database management system, open to the public

DB Browser for SQLite is a visual tool that's used to create, design and edit database
files compatible with SQLite.

2.The query writing area

Let's take a look at the third important area that we should get familiar with in our
DB Browser for SQLite database software. 

Now, let's take a look at the Execute SQL tab. Now, let me point out some main components
that we should take a note of at the moment.

- query pane - I'm just typing in random words at the moment, but this is where we'll
be composing our queries
- result pane - we will have an area to observe the results of executing a query
- message pane "Execution finished without errors". If we compose a query, observe
the result, the messages pane tells us if that query has run without error. It tells us
how long that query took to run, and a lot of other vital information that's going to
be useful to us as SQL practitioners. 

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

##### Discovering Insights in Data

1.Types of SQL operators

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

2.Filter and analyze numeric data

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

3.BETWEEN and IN operators

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

4.Filter and analyze text data

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

5.Search records without an exact

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

6.Filter and analyze using dates

So far, we've analyzed NUMERIC and TEXT data. Now, we analyze DATE data.






Test

1.The Basics of Database Structures

- How does a table differ from other data organization methods?

    - [x] It is two-dimensional.
          The defining features of a table are the rows and columns.
    - [ ] It contains records.
    - [ ] It has headings.

2.The SQL Stack

- Which strategy should you use for learning SQL?

    - [ ] Examine a case study in detail.
    - [ ] Read everything you can find.
    - [ ] Create several different databases.
    - [x] Practice translating questions into structured queries.
          Going through the process of typing commands and perfecting syntax is very
          helpful.

3.The SQLite Database Environment

- After reviewing the Database Structure tab, how many columns does the Employee table
  of the WSDA Music exercise file database have?

    - [ ] 7
    - [ ] 16
    - [ ] 18
    - [x] 15
          This can be found by expanding the employee table in the database structure
          tab.

- After reviewing the Database Structure tab in DB Browser, how many tables are in
  the WSDA Music exercise file database?

    - [ ] 22
    - [ ] 5
    - [x] 11
          This can be found in the database structure tab under tables.
    - [ ] 10

- You have just typed a query in the query pane. How do you execute it?

    - [ ] Open the query.
    - [x] Press the Play button.
          There are two Play buttons: one to execute the current line and one to
          execute all lines.
    - [ ] Press the Save-and-Run button.
    - [ ] Type Execute.

- After reviewing the Database Structure tab, what fields are contained in the Genre
  table of the WSDA Music exercise file database?

    - [x] GenreId and Name
          This can be found by expanding the Genre table in the Database Structure
          and noting the fields contained within.
    - [ ] CustomerId and Total
    - [ ] Name
    - [ ] GenreId, Total, and Id

- After reviewing the Database Structure tab, what are some of the datatypes in the
  Employee table of the WSDA Music exercise file database?

    - [x] Integer, DateTime, and Nvarchar
          These are all valid datatypes in the employee table. This is found under 'Type'
          in the database structure tab in the expanded employee table.
    - [ ] Byte, Bit, and Date
    - [ ] Time, Date, and Datum
    - [ ] Number, Data, and Fraction

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

