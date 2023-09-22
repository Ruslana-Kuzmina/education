# Adding, Modifying and Deleting data

## 1.Analysis and administration

Фdding, updating, and deleting changes or manipulates the data in our database in
some way. In SQL, there are a few specific set of commands that together are called
**data manipulation language or DML** for short and these are SQL statements used
to change or alter data stored in the tables of a database. 

DML is more commonly used in roles, such as database developer and database administrator
that oversee the growth, improvement, and management of the company's database.

## 2.Inserting data

Everything that we've taken a look at, as far as SQL code or syntax, did not modify
any data in our database. The statements that are referred to as DML or Data Manipulation
Language are the statements that actually do cause some sort of alteration to our
existing data. So the official statements that are referred to as DML are insert,
update, and delete. And as these names imply, these statements can be used to add,
modify, and remove data from the tables in your database.

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: DML | Inserting Data | Add an additional artist to our existing catalog
*/

INSERT INTO
  Artist (Name)
VALUES ('Bob Marley')
```

Now, to add data to our database, the **INSERT statement** is actually used to accomplish
this.

## 3.Updating data

UPDATE statement

- modifiies existing data
- used with the WHERE clause

WHERE clause - spesifies the row of data to update

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: DML | Updating Data | Add an additional artist to our existing catalog
*/

UPDATE
  Artist
SET Name='Damien Marley'
WHERE
  ArtistId=276
```

## 4.Deleting data

DELETE statement - removes existing records from a table

Without the WHERE clause, using a DELETE statement will delete every single record
from your table.

```sql
/*
Created By: Ruslana Kuzmina
Create Data: mm/dd/yyyy
Description: DML | Deleting Data
*/

DELETE FROM
  Artist
WHERE
  ArtistId=276
```

Tests:

- To which field does the following code add data?

```sql
INSERT INTO
   Congo (Alpha)
VALUES (4267)
```

    - [x] Alpha
          "Alpha" is a field in the table "Congo".
    - [ ] 4267
    - [ ] Congo