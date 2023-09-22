# Stored queries

## 1. View Introduction

There is, with something called Views in SQL.

A **view** is simply a query that's saved and can be executed repeatedly or referenced
by other queries. Views are helpful for a number of reasons, but convenience is
definitely the main one. A view is the perfect solution for repeatedly generating
a report of all albums, their associated tracks, and the artist who sang them. 

## 2.Creating a new

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Views
*/

CREATE VIEW V_Avgtotal AS
SELECT
  round(avg(total),2) AS [Average Total]
FROM
  Invoice
```

In SQL, a view is a virtual table based on the result-set of an SQL statement.

A view contains rows and columns, just like a real table. The fields in a view are
fields from one or more real tables in the database.

You can add SQL statements and functions to a view and present the data as if the
data were coming from one single table.

A view always shows up-to-date data! The database engine recreates the view, every
time a user queries it.

## 3.Editing a view

View Editing Process:

- differs depending on the request

Views in SQLite are not modified with syntax - they are deleted, than recreated.

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Views
*/

CREATE VIEW V_Avgtotal AS
SELECT
  avg(total) AS [Average Total]
FROM
  Invoice
```

We use the tab Database Structure, click on the field Views right click and choose
 command "Modify View".

## 4.Joining views

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Views and Joins
*/

CREATE VIEW V_Tracks_InvoiceLine AS
SELECT
  il.InvoiceId,
  il.UnitPrice,
  il.Quantity,
  t.Name,
  t.Composer,
  t.Milliseconds
FROM
  InvoiceLine il
INNER JOIN
  Track t
ON
  il.TrackId=t.TrackId
```

## 5.Deleting views

Working with Views:

- creating
- modifying
- deleting

This is by going to our database structure and when we right-click, last option here
which is to delete a view.

Another approach - use SQL statement

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Deleting a Views
*/

DROP VIEW
  V_AvgTotal
```

Tests:

- If Amelia wants to change a view, then what should she do first?

  - [ ] Create a new name.
  - [x] Drop the view.
        Amelia may drop or modify the view from the Database Structure tab or from
        the Execute SQL tab.
  - [ ] Move the view.

- Every week, Pilar must generate a summary and comparison report from five tables
  listing the results of different experimental trials. How should Pilar proceed?

  - [x] Create a view containing the important queries.
        The view will allow Pilar to run the same query repeatedly with little
        additional effort.
  - [ ] Combine the five tables into one.
  - [ ] Export the tables to a spreadsheet.

