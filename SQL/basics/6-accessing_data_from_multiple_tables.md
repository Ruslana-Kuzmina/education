# Accessing Data from multiple tables

## 1.How tables share a relationship

Join is a command that combines the fields from two or more tables in a relational
database

```sql
/*

Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: JOINS

*/

SELECT
  *
FROM
  Invoice INNER JOIN Customer
  ON Invoice.CustomerId=Customer.CustomerId
```

We also have a star symbol (*) after SELECT, and what this is, instead of specifying
a column that we want to return, this returns every single column that is in both
the customer and invoice table. We are selecting all the fields from the invoice
table and joining them to all the fields in the customer table. We use the keyword
on to provide the query with the link between these two tables, which are the customerID
field in the invoice table to the customerID field in the customer table. Since there
are two versions of the customerID field, one in each table, we have to use this
particular notation, which is table name followed by field name to specify exactly
which field in which table we're interested in joining. All together, we now have
a new syntax, which represents a join between the invoice and the customer table.

```sql
/*

Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: JOINS

*/

SELECT
  *
FROM
  Invoice
INNER JOIN
  Customer
ON
  Invoice.CustomerId=Customer.CustomerId
ORDER BY
  Customer.CustomerId
```

An entity relationship diagram (ERD) is a graphical representation of the relationship
between our tables.

In a relational database, the process of distributing fields across related tables is
known as normalization. And normalization keeps the size of our database small, as
it reduces the need to duplicate or make mention of data in multiple places.

## 2.Simplifying JOINs

```sql
/*

Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: JOINS

*/

SELECT
  c.FirstName,
  c.LastName,
  i.InvoiceId,
  i.CustomerId,
  i.InvoiceDate,
  i.total
FROM
  Invoice AS i
INNER JOIN
  Customer AS c
ON
  i.CustomerId=c.CustomerId
ORDER BY
  c.CustomerId
```

## 3.Types of JOINs

How we've used JOIN Clauses

- accessed fields in multiple tables
- identified primary keys
- identified similar foreign keys
- used ON keyword to link the tables together

Discrepancies between tables are handled with different types of joins.

## 4.The INNER JOIN

An inner join only returns matching records. Any unmatched data from either table
is ignored. Joins are often described with the use of Venn diagrams. As our Venn
diagram shows, an inner join represents only the overlapping section of the Venn
diagram. Now, the inner join is the most common type of join that's used, and the
main use of the inner join is to bring corresponding data together from different
tables in a relational database.

```sql
SELECT
FROM
  Invoice AS i
INNER JOIN
  Customer AS c
ON
  i.CustomerId=c.CustomerId
```

## 5.The LEFT JOIN

```sql
SELECT
FROM
  Invoice AS i
LEFT OUTER JOIN
  Customer AS c
ON
  i.CustomerId=c.CustomerId
```

A left outer join combines all the records from the left table with any matching
records from the right table. As shown in our Venn diagram, the concept of left table
and right table depends entirely on the order these tables are listed in the join
statement.

And in this instance, our invoice table is the left table and our customer table
is the right table. With this type of join, everything in our invoice table will
be displayed.

We're simply replacing inner join with left outer join instead. We see that the SQL
browser has added nulls or null data to our results set. Remember that we have no
information in the customer table about customer six. Adding null data is how the SQL
browser handles the fact that we are trying to match five records from the invoice
table to only four records from the customer table. 

Left joins are useful because they allow us to see discrepancies in our data. We can
produce lists of customers that have not generated invoices or search for data that
has been removed in the right table but still exist in the left.

## 6.The RIGHT JOIN

```sql
SELECT
FROM
  Invoice AS i
RIGHT OUTER JOIN
  Customer AS c
ON
  i.CustomerId=c.CustomerId
```

Right outer joins are not supported in SQL Light. 

The right outer join returns the entire right table as well as matching information
from the left table. The right join is a mirror image of the left join, and functions
in a very similar way. Now, similar to what occurred in the

## 8.Joining many tables

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: JOINS on more than two tables | What employees are responsible for the
10 highest individual sales?

*/

SELECT
  e.FirstName,
  e.LastName,
  e.EmployeeId,
  c.FirstName,
  c.LastName,
  c.SupportRepId,
  i.CustomerId,
  i.total
FROM
  Invoice AS i
INNER JOIN
  Customer AS c
ON 
  i.CustomerId=c.CustomerId
INNER JOIN
  Employee AS e
ON 
  c.SupportRepId=e.EmployeeId
ORDER BY
  i.total DESC
LIMIT 10
```

Tests:

- Why would you join three or more tables?

  - [x] The necessary information is not available in fewer tables.
        You may need information from all tables, or some tables may serve simply
        to link data.
  - [ ] There are too many tables in your database.
  - [ ] You need to create a central repository.
  - [ ] You need to reduce storage requirements.

- What is the function of the ON portion of a JOIN clause?

  - [ ] It creates the name for the resulting combination.
  - [ ] It limits the total number of output records.
  - [x] It specifies the matching condition for combining records.
        For example, the user might specify that the second column of table A should
        match the sixth column of table B.