# SQL Commands

The commands in SQL are call queries, and they are two types of queries:

- Data Definition queries (DDL)
    - Statements_
        - CREATE
        - ALTER
        - DROP
        - TRUNCATE
        - RENAME
        - COPY

- Data Manipulation queries (DML)
    - Statements
        - INSERT
        - UPDATE
        - DELETE
        - WITH

> **NOTE**: For convenience, let's call the Queries commands
### Content Table
- [Table Constraints](#table-constraints)

- [Basics SQL Commands](#basic-sql-commands)
    - [Create Table](#create-table)
    - [Alter Table](#alter-table)
    - [Drop Table](#drop-table)
    - [Truncate Table](#truncate-table)
    - [Insert Data](#insert-data)
    - [Update Data](#update-data)
    - [Rename Table](#rename-table)
    - [Copy Table](#copy-table)
- [Data Types](DTP)

- [Constrint Types](TOC)

## Basic SQL Commands
The commands in this section are the most basic commands in SQL, and they are used to create, modify, and delete tables.
> **Note:** The commands in this section are DDL commands.


### **Create Table**: This command is used to create a table in the database.
```` SQL
CREATE TABLE table_name (
    column_name1 data_type,
    column_name2 data_type,
    column_name3 data_type,
    );
````
Example:
```` SQL
CREATE TABLE employees (
    id INT constraint employee_pk PRIMARY KEY,
    name VARCHAR(25),
    age INT,
    address VARCHAR(25),
    salary DOUBLE,
    );
````
> **Note:** The PRIMARY KEY constraint uniquely identifies each record in a table. Primary keys must contain UNIQUE values, and cannot contain NULL values. A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

### **Alter Table**: This command is used to modify the structure of a table.
- **Add Column**: This command is used to add a new column to a table.

- **Drop Column**: This command is used to delete a column from a table.

- **Modify Column**: This command is used to modify the data type of a column.
```` SQL
ALTER TABLE table_name ADD column_name data_type;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY COLUMN column_name data_type;
````
Example:
````SQL
ALTER TABLE employees ADD email VARCHAR(25);
````

````SQL
ALTER TABLE employees DROP COLUMN address;
````
> **Note:** If you want to delete multiple columns, you can use a comma to separate the column names.

````SQL
ALTER TABLE employees MODIFY COLUMN salary DOUBLE(10,2);
````
### **Drop Table**: This command is used to delete a table from the database.
```` SQL
DROP TABLE table_name;
````
> **Note:** Be careful before using this command, because once you delete a table, all the information in that table will be lost.

### **Truncate Table**: This command is used to delete all the records from a table, but the table structure and its columns, constraints, indexes, and so on remain.
```` SQL
TRUNCATE TABLE table_name;
````
> **Note:** Be careful before using this command, because once you delete all the records from a table, all the information in that table will be lost.

### Insert Data: This command is used to insert data into a table.
```` SQL
INSERT INTO table_name (
    column1,
    column2,
    column3, ...)
VALUES (value1, value2, value3, ...);
````
### **Update Data**: This command is used to modify the existing records in a table.
```` SQL
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
````
> **Note:** If you omit the WHERE clause, all records in the table will be updated!
### **Rename Table**: This command is used to rename a table.
```` SQL
RENAME TABLE table_name TO new_table_name;
````
### **Copy Table**: This command is used to copy a table.
```` SQL
CREATE TABLE new_table_name AS
    SELECT * FROM old_table_name;
````
> **Note:** The new table will be created with the column-names and types as defined in the old table. You can also select only some columns, and give them new names, like this:
```` SQL
CREATE TABLE new_table_name AS
    SELECT column_name1, column_name2, column_name3
    FROM old_table_name;
````
continue...
