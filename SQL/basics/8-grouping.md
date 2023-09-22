# Grouping

## 1.Grouping your query results

The **Group By** clause is often used with aggregate functions like:

- Count
- Max
- Min
- SUM
- AVG

## 2.Filtering with a grouped condition

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Grouping in SQL | What are the average invoice totals by city?
*/

SELECT
  BillingCity,
  round(AVG(total),2)
FROM
  Invoice
GROUP BY
  BillingCity
ORDER BY 
  BillingCity
```

GROUP BY cause groups by the field or the column that is not aggregated (BillingCity
in our case)

## 3.Grouping with the WHERE clause

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Grouping in SQL | What are the average invoice totals by city for only
the cities that start with L?
*/

SELECT
  BillingCity,
  round(AVG(total),2)
FROM
  Invoice
WHERE
  BillingCity LIKE 'L%'
GROUP BY
  BillingCity
ORDER BY 
  BillingCity
```

We were able to include the WHERE clause and apply filtering to our non-aggregated
field. You were able to filter down to only the cities that started with L by way
of our WHERE clause which was applied to the billing city which in our example here
is the non-aggregated field.

## 4.Grouping with the HAVING clause

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Grouping in SQL | What are the average invoice totals by city greater
than 5.00$?
*/

SELECT
  BillingCity,
  round(AVG(total),2)
FROM
  Invoice
GROUP BY
  BillingCity
HAVING
  AVG(total)>5
ORDER BY 
  BillingCity
```

There are times where we will need to use criteria on fields that have been aggregated,
for instance, like our average total here.

At least in this case, that we cannot use the WHERE clause to create a condition based
on an aggregate function.

If we want additional filtering based on the aggregate function, we do need to include
a secondary filtering clause and this clause is referred to as the HAVING clause.

The HAVING clause always comes after the GROUP BY clause.

## 5.Grouping with the WHERE and HAVING clause

The difference between the WHERE versus the HAVING clause is the WHERE clause is for
filtering non aggregate data and the HAVING is for filtering results that contain
aggregates.

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Grouping in SQL | What are the average invoice totals by city greater
than 5.00$ for cities starting with B?
*/

SELECT
  BillingCity,
  round(AVG(total),2)
FROM
  Invoice
WHERE
  BillingCity LIKE 'L%'
GROUP BY
  BillingCity
HAVING
  AVG(total)>5
ORDER BY 
  BillingCity
```

This filtering step WHERE clause is performed before the HAVING and ORDER BY clauses
are processed. Since we must filter before we can group the order of these filtering
clauses is important and the WHERE is most always coming before the HAVING.

## 6.Grouping by many fields

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: Grouping by more the one field at a time? | What are the average invoice
totals by billing country and city?
*/

SELECT
  BillingCountry,
  BillingCity,
  round(AVG(total),2)
FROM
  Invoice
GROUP BY
  BillingCountry, BillingCity
ORDER BY 
  BillingCountry
```

Tests:

- What is wrong with the following query?

```sql
SELECT SubUrb, Round(AVG(HouSiz),1)
FROM Housing
GROUP BY SubUrb
WHERE SubUrb LIKE '%Lake'
```

    - [ ] The WHERE clause should not use a wildcard.
    - [x] The WHERE clause should come before the GROUP BY clause.
          It makes more sense to filter the results before grouping them.
    - [ ] HouSiz should be rounded to two decimal places.
    - [ ] The results should be grouped by housing size.

- Jamal has a large database with internet traffic listed by address, city, county,
  and state. Why would he group aggregate results by both city and county?

    - [ ] to order the results first by county and then by city
    - [ ] to eliminate the state field from the results
    - [x] to distinguish Hart in Bell county from Hart in Joshua county
          If Jamal only grouped by city, then there would be one entry for Bell.
    - [ ] to see countywide aggregates