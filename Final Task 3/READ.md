# Final Lab Task 3: Table Manipulation #


## Task 1 - Viewing Data and Table Structure ## 


In this task, we want to view all the data in the products_tbl table and see how the table is structured.

```sql
SELECT * FROM products_tbl; 
```
This command gets all the rows and columns in the products_tbl table.

```sql
DESCRIBE products_tbl; 
```

This command shows the structure of the products_tbl table (e.g., column names, data types, and if they can be left empty).

## Task 2 - Creating and Modifying the Table ##

Here, we create a new database and table. We also add some data to the table.

```sql
CREATE DATABASE products_db;
USE products_db; 
```

The first command creates a new database called products_db.

The second command makes products_db the active database, so we can work with it.

```sql
CREATE TABLE products_tbl ( 
id INT AUTO_INCREMENT PRIMARY KEY, 
product_name VARCHAR(100) NOT NULL, 
price DECIMAL(10, 2) ); 
```

This creates a table called products_tbl with three columns:

id: An integer number that automatically increases every time we add a new product.
product_name: A column for the name of the product, which cannot be left empty.
price: A column for the product price, with two decimal places.

ALTER TABLE products_tbl ADD CONSTRAINT chk_price CHECK (price > 0); 

This command adds a rule (called a constraint) to make sure that the price is always greater than 0. We don’t want products with a negative or zero price.

```sql
INSERT INTO products_tbl (product_name, price) VALUES ('Laptop', 999.99), ('Smartphone', 599.99), ('Tablet', 299.99), ('Keyboard', 19.99), ('Mouse', 14.99), ('Desk Lamp', 24.99), ('Speakers', 9.99); 
```

These commands add seven products to the table with their names and prices.

```sql
ALTER TABLE products_tbl MODIFY COLUMN product_name VARCHAR(120) NOT NULL; 
```
This command increases the size of the product_name column from 100 to 120 characters to allow for longer product names.

## Task 3 - Table Diagram ## 
Here’s a diagram showing the table structure:

 <img src="https://github.com/ninabel2005/Escanan/blob/main/Final%20Task%203/Files/image.png" alt="Alt Text" width="800" height="400"> 

 
This diagram helps to visualize the table and its columns.

## Task 4 - SQL Script for Database and Table ## 

This is the full SQL code that creates the database, table, and adds the data. You can use it to set up the table on any MySQL server.

 ```sql
CREATE DATABASE products_db; USE products_db;
CREATE TABLE products_tbl ( id INT AUTO_INCREMENT PRIMARY KEY, product_name VARCHAR(100) NOT NULL, price DECIMAL(10, 2) );
ALTER TABLE products_tbl 
ADD CONSTRAINT chk_price CHECK (price > 0); 
INSERT INTO products_tbl (product_name, price) VALUES ('Laptop', 999.99), ('Smartphone', 599.99), ('Tablet', 299.99), ('Keyboard', 19.99), ('Mouse', 14.99), ('Desk Lamp', 24.99), ('Speakers', 9.99);
ALTER TABLE products_tbl MODIFY COLUMN product_name VARCHAR(120) NOT NULL;
SELECT * FROM products_tbl;
DESCRIBE products_tbl;
```
