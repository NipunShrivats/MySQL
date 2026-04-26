# MySQL Database

## Relational Database (SQL)

1. A structured way of storing data in tables (rows and columns) where relationships between different tables are defined using keys, it is the most widely used database miodels today, providing systems like MySQL, PostgreSQL and Oracle.

### Core concepts:-

1. Rows(Tuples): Each row represents a record (eg. one customer).
2. Column (Attributes): Each column represents a property of that record (eg, customer, name, ID, email).
3. Primary Key: A unique identifeir for each row(eg. customer ID).
4. Foreign Key: A column that links one table to another, esablishing relationships.
5. Relationships: Tables can be connected (one-to-one, one-to-many, many-to-many) using keys.

### NOTE:-

A row goes Horizontaly from left t o right containg record on one customer containg like its id, name address etc.
and a column only have one type of data of many custonmers like either id or name or address.

## Non-Relationl Database (NoSQL)

Root login on console

mysql -u root -p
masterkey

mysql -u nipun -p
password:-this

# Data Types

1. INT: Integer type, used for whole numbers.
2. VARCHAR(x): Variable-length string, up to x characters.
3. ENUM: A String object width a value chosen from a list of permitted values. eg. gender ENUM("Male", "Female", "Other").
4. DATE: Stores date values eg. date_of_birth DATE
5. TIMESTAMP: Store s date and time, automatically set to the current timestamp when a row is created.
6. BOOLEAN: Stores TRUE or FALSE values, often used for flags like is_active.

# Constraints

They are the rules applied to columns or tables that enforce data integretty, accuracy, and validity.
They prevent invalid, duplicate, or inconsistent data from being stored in your database.

types:-

1. AUTO_INCREMENT: Automatically generates a unique number for each row.
2. PRIMARY KEY: Uniquely identifies each row in the table.
3. NOT NULL: Ensures all values in a column are different.
4. DEFAULT: Sets a default value for a column if no value is provided
   eg:-
   created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP;
   or
   is_active BOOLEAN DEFAULT TRUE;

# Queries

1. Create a Database

   ```
   CREATE DATABASE startersql;
   ```

2. Delete Database

   ```
   DROP DATABASE startersql;
   ```

3. start using a database

   ```
   USE startersql;
   ```

4. Create a table

```
CREATE TABLE users (
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(100) NOT NULL,
email VARCHAR(100) UNIQUE NOT NULL,
gender ENUM('Male', 'Female', 'Other'),
date_of_birth DATE,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

```

5. Select data from table

   ```
   SELECT * FROM users;
   ```

6. Select specific columns

   ```
   select name, email from users;
   ```

7. Renaming a table

   ```
   RENAME TABLE users to programmers;
   ```

8. Alter Table (add column)

   ```
   ALTER TABLE users ADD COLUMN is_Active BOOLEAN DEFAULT true;
   ```

9. Alter Table (delete column)

   ```
   ALTER TABLE users DROP COLUMN is_active
   ```

10. Alter Table (shift columns)

    ```
    ALTER TABLE users MODIFY COLUMN email VARCHAR(100) AFTER id;
    ALTER TABLE users MODIFY COLUMN date_of_birth DATE FIRST;
    ```

# CRUD

1. Adding Data in table

   ```
   INSERT INTO users VALUES
   (DEFAULT, "Nipun", "nipun.rawat@gmail.com", "Male", "2000-08-08", DEFAULT);
   ```

   ```
   INSERT INTO users (name, email, date_of_birth) VALUES
   ("Sonia", "sonia.sharma@gmail.com", "2000-03-07"),
   ("ram", "ram.sharma@gmail.com", "2000-05-07");
   ```

2.
