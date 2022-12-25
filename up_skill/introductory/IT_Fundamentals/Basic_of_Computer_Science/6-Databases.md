# Databases

## Information Storages

Methods for storing data:

- Text file

We could save all information in structured text files like the one provided.
The first row is dedicated to a record type of information stored about each
customer: a customer’s name and address. Each row, starting from the second one,
is a record. Each field in a row is separated with commas. This type of a
structured file has a special name. It is a comma separated values (csv) file.
This type of information storage can be used if the amount of data is relatively
small.

- Spreadsheet

Alternatively, we could use a spreadsheet software like Microsoft Excel to store
our data. The data is now easier to read as it is organized in rows and columns.
We can sort and format data. Updating data manually is relatively easy if the
amount of records is within reasonable numbers. However, it is hard and slow for
any other program to read or write spreadsheets due to their specific storage format.

- Database

The best approach is to use a database management system. It may look like an
advanced spreadsheet program if you use a viewer program to view the data, but
its power lies in the fact that it has built-in capabilities to manage data.
Another program can interact with a database and tell it to retrieve a specific
record, or to update or delete an existing record, or to add a new one. In databases,
data are usually clearly structured and quite intuitive. While you do not always
have to know the internal format of the data in a database, you should understand
how they are interpreted and stored. What else you need to know is how to interact
with the database.

There are many types of databases nowadays:

- **Relational Dataases** - The data is stored in tables, some of which are
  related to each other. Each row in the table is a record with a unique ID called
  the key. The columns of the table hold attributes of the data, and each record
  usually has a value for each attribute.
- **Object-Oriented Databases** - Information in an object-oriented database is
  represented in the form of objects, as in object-oriented programming.
- **Distributed Databases** - consists of several files located in different
  sites. The database may be stored on multiple servers, located in the same physical
  location, or distributed over different networks.
- **Data warehouses** - is a type of database designed for fast query and analysis.
- **NoSQL database** - does not use the relational model and does not use SQL
  for a database query. NoSQL is a very broad term. There are many types of NoSQL
  databases.

Most used type of databases is a **relational database**. The data in the relational
database is stored in tables. Each row in the table is a record with a unique ID
called the key. The columns of the table hold attributes of the data, and each
record usually has a value for each attribute. A relational database provides the
most reliable way to access structured information. Virtually all relational
databases use structured query language (SQL) for writing and querying data.

Relational databases are called that way because they usually contain multiple
tables, some of which are related to each other. Each row in a table has its own
unique key. Rows in a table can be linked to rows in other tables by having an
additional column containing the key of the linked row. Such columns are called
foreign keys. Let us have a look at the example.

Among relational databases, the most popular relational database management
systems are:

- Oracle database
- MySQL
- Microsoft SQL Server
- PostgreSQL

## SQL Commands

SQL stands for Structured Query Language. It is the language that you use to
interact with a relational database. Using SQL, you can create new records,
delete, and update existing ones. You can also change the structure of a database,
create new tables, delete existing ones, change, add or delete fields in the table.

The most important SQL commands are:

SELECT – retrieves the data from a database,
UPDATE – updates the data in a database,
DELETE – deletes the data from a database,
INSERT INTO (or INSERT) – inserts new data into a database,
ORDER BY ASC/DESC – sorts the data in ascending or descending order,
CREATE TABLE – creates a new table,
ALTER TABLE – modifies a table,
DROP TABLE – deletes a table,
JOIN – combines rows from two or more tables, based on a related column,
FROM – a clause used to list the tables and any joins required for the SQL statement,
WHERE – a clause used to specify a condition while fetching the data from a single
table or by joining with multiple tables.

The SQL commands INSERT, SELECT, UPDATE, and DELETE corresponds to the four basic
principles of persistent storage: create, read, update, and delete (CRUD), respectively.
