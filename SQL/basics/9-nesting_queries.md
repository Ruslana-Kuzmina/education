# Nesting Queries

## 1.Subqueries and aggregate functions

**Nested query** - a query wrapped inside of another query

The wrapping is just an open and closed parenthesis or brackets that surround the
query.

How each individual city was performing against the global average sales?

- global average sales amount
- average sales per city

## 2.SELECT clause subquery

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Subqueries | Gather data about all invoices that are less than this average?
*/

SELECT                       |
  InvoiceDate,               |
  BillingAddress,            |
  BillingCity,               |
  total                      |    Outer Query
FROM                         |
  Invoice                    |
WHERE                        |
  total<                     |
  (select avg(total) from invoice) | Inner Query
ORDER BY                     |
  total DESC                 |    Outer Query
```

The original query that we started off with is referred to as the outer query and
the part that goes inside of the parentheses is referred to as the inner query.

## 3.Aggregated subqueries

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Subqueries in the SELECT | How is each individual city performing against
the global average sales?
*/

SELECT
  BillingCity,
  AVG(total) AS [City Average],
  (select avg(total) from invoice) AS [Global Average]
FROM
  Invoice
GROUP BY
  BillingCity
ORDER BY
  BillingCity
```

## 4.Non-aggregate subqueries

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Subqueries without aggregate function
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity
FROM
  Invoice
WHERE
  InvoiceDate>
(SELECT
  InvoiceDate
FROM
  Invoice
WHERE
  InvoiceId=251)
```

We've effectively responded to the question of, give us all the invoices that have
occurred after this particular date.

## 5.IN clause subquery

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Return multiple values from a subquery
*/

SELECT
  InvoiceDate,
  BillingAddress,
  BillingCity
FROM
  Invoice
WHERE
  InvoiceDate IN
(SELECT
  InvoiceDate
FROM
  Invoice
WHERE
  InvoiceId IN(251, 252, 254))
```

We are asked if any purchases were made on these particular days. If we want to
select all invoices for those three days, we can either start a brand new query,
or we can just use our existing query here as a subquery.

Because we are anticipating multiple rows in our outer query, we've now equipped
it with a WHERE clause, as well as the IN operator, which as we know, can handle
multiple records.

And it now responds effectively to them, telling them if any other purchases were
made on those three original dates. Now, this technique of turning an existing query
into a subquery, is pretty useful when you're dialing in on your data.

## 6.DISTINCT clause subquery

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Subqueries and DISTINCT. Which tracks are not selling?
*/

SELECT
  TrackId,
  Composer,
  Name
FROM 
  Track
WHERE
  TrackId
NOT IN
(SELECT
  DISTINCT
  TrackId
FROM
  InvoiceLine
ORDER BY
  TrackId)
```

The SELECT DISTINCT statement is used to return only distinct (different) values.

Inside a table, a column often contains many duplicate values; and sometimes you
only want to list the different (distinct) values.

Tests:

- What does the following WHERE clause accomplish?

```sql
WHERE ConcertCity IN
(SELECT ConcertCity
FROM Concerts
WHERE ConcertCntry IN ('US', 'UK', 'DE')
```

  - [x] It limits ConcertCity to those in the countries US, UK, and DE.
        The subquery returns all concert cities in the US, UK, or DE.
  - [ ] It returns all concert cities not in the US, UK, or DE.
  - [ ] It provides the country abbreviation for all concerts.
  - [ ] It lists all cities in the Concert database.

- What is wrong with the following WHERE clause?

```sql
WHERE dist  >  AVG(dist) from Loc
```

  - [x] The subquery should be enclosed in parentheses and begin with SELECT.
        The syntax for a subclause follows the same rules as a regular clause.
  - [ ] The field dist should not appear twice in the same clause.
  - [ ] The round function should operate on AVG(dist).
  - [ ] The subquery should be enclosed in brackets and end with RETURN.

