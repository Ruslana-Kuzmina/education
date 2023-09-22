# Practice

## Challenge 1

General queries that begin to give you some high-level context:

1.How many transactions took place between the years 2011 and 2012?
2.How much money did WSDA Music make during the same period?

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: How many transactions took place between 2011 and 2012?
*/

SELECT
  COUNT(*)
FROM
  Invoice
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
```

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: How much money did WSDA Music make during between 2011 and 2012?
*/

SELECT
  SUM(total)
FROM
  Invoice
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
```

## CHALLENGE 2

More targeted questions that query tables containing data about customers and employees

1.Get a list of customers who made purchases between 2011 and 2012.
2.Get a list of customers, sales reps, and total transaction amounts for each customer
between 2011 and 2012.
3.How many transactions are above the average transaction amount during the same
time period?
4.What is the average transaction amount for each year that WSDA Music has been
in business?

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Get a list of customers who made purchases between 2011 and 2012
*/

SELECT
  c.FirstName,
  c.LastName,
  i.total
FROM
  Customer c
Inner Join
  Invoice i
ON
  c.CustomerId=i.CustomerId
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
ORDER BY
  i.total DESC
```

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Get a list of customers, sales reps, and total transaction amounts
for each customer between 2011 and 2012.
*/

SELECT
  c.FirstName AS [Customer FirstName],
  c.LastName AS [Customer LastName],
  e.FirstName AS [Employee FirstName],
  e.LastName AS [Employee LastName],
  i.total
FROM
  Invoice i
INNER JOIN
  Customer c
ON
  i.CustomerId=c.CustomerId
INNER JOIN
  Employee e
ON
  e.EmployeeId=c.SupportRepId
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
ORDER BY
  i.total
```

We devite for 2 small requets: 

- average transaction
- how many transactions are above the average transaction

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: How many transactions are above the average transaction amount during
the same time period?
*/

SELECT
 round(avg(total),2) AS [Average Transaction]
FROM
  Invoice
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
```



```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: How many transactions are above the average transaction amount during
the same time period?
*/

SELECT
 count(total) AS [Number of transactions]
FROM
  Invoice
WHERE
  total>
  (SELECT
  round(avg(total),2) AS [Average Transaction]
  FROM
  Invoice
  WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31')
  AND date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
```

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: What is the average transaction amount for each year that WSDA Music has been
in business?
*/

SELECT
  round(avg(total),2) AS [Average transaction amount],
  strftime('%Y', InvoiceDate) AS [Year]
FROM
  Invoice
GROUP BY
  strftime('%Y', InvoiceDate)
```

## CHALLENGE 3

Queries that perform in-depth analysis with the aim of finding employees who may
have been financially motivated to commit a crime

1.Get a list of employees who exceeded the average transaction amount from sales they
generated during 2011 and 2012.
2.Create a Commission Payout column that displays each employee’s commission
based on 15% of the sales transaction amount.
3.Which employee made the highest commission?
4.List the customers that the employee identified in the last question.
5.Which customer made the highest purchase?
6.Look at this customer record—do you see anything suspicious?
7.Who do you conclude is our primary person of interest?

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Get a list of employees who exceeded the average transaction amount
from sales they generated during 2011 and 2012.
*/

SELECT
 e.FirstName,
 e.LastName,
 sum(i.total) AS [Total Sales]
FROM
 Invoice i
INNER JOIN
 Customer c
ON
 i.CustomerID=c.CustomerId
INNER JOIN
 Employee e
ON
 e.EmployeeId=c.SupportRepId
WHERE 
  i.total>
  (SELECT 
  round(avg(total),2) AS [Average Transaction Amount]
  FROM
  Invoice
  WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31') 
AND date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
GROUP BY
  e.FirstName,
  e.LastName
```

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Create a Commission Payout column that displays each employee’s commission
based on 15% of the sales transaction amount.
*/

SELECT
  e.FirstName,
  e.LastName,
  sum(i.total) AS [Total Sales],
  round(sum(i.total)*0.15,2) AS [Commission Payout]
FROM
  Invoice i
INNER JOIN
  Customer c
ON
  i.CustomerId=c.CustomerId
INNER JOIN
  Employee e
ON
  e.EmployeeId=c.SupportRepId
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
GROUP BY
  e.FirstName,
  e.LastName
```

Which employee made the highest commission?

Jane Peacock

This result is appeared from the previous request

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Create a Commission Payout column that displays each employee’s commission
based on 15% of the sales transaction amount. List the customers that the employee
Jane Peacock supported?
*/

SELECT
  c.FirstName,
  c.LastName,
  e.FirstName,
  e.LastName,
  sum(i.total) AS [Total Sales],
  round(sum(i.total)*0.15,2) AS [Commission Payout]
FROM
  Invoice i
INNER JOIN
  Customer c
ON
  i.CustomerId=c.CustomerId
INNER JOIN
  Employee e
ON
  e.EmployeeId=c.SupportRepId
WHERE
  date(InvoiceDate)>='2011-01-01' AND date(InvoiceDate)<='2012-12-31'
  AND e.LastName='Peacock'
GROUP BY
  c.FirstName,
  c.LastName,
  e.FirstName,
  e.LastName
```

Which customer made the highest purchase?

I added to the request 

```sql
ORDER BY
  [Total Sales] DESC
```

Result: John Doeein

Look at this customer record—do you see anything suspicious?

```sql
SELECT
  *
FROM
  Customer
WHERE
  LastName='Doeein'
```

We do have the first and last names, but then we have no other information except
for the support rep ID, which is support rep ID number three. So this is quite a
odd record seeing that none of the other fields are filled in.

Who do you conclude is our primary person of interest?