# Hands-on-Project-CREATE-ALTER-TRUNCATE-DROP-into-Tables-using-PostgreSQL

In this project, I demonstrated skills in writing SQL statements to create tables and load data in PostreSQL.

# Software Used in this Lab

PgAdmin 4 (PostgreSQL 15)

# Database Used in this Lab

Data used in this project were gotten from IBM

# Objectives

The objectives of this project were to: 

1. Create a database.
2. Create a new table in a database.
3. Add, delete, or modify columns in an existing table.
4. Remove all rows from an existing table without deleting the table itself.
5. Delete an existing table in a database

# Highlights

- How does the syntax of a CREATE statement look?
  
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);

- How does the syntax of an ALTER statement look?

ALTER TABLE table_name
ADD COLUMN column_name data_type column_constraint;

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE table_name
ALTER COLUMN column_name SET DATA TYPE data_type;

ALTER TABLE table_name
CHANGE current_column_name new_column_name;

- How does the syntax of a TRUNCATE statement look?

TRUNCATE TABLE table_name;

- How does the syntax of a DROP statement look?

DROP TABLE table_name;

# Task A: Creating a tables

1. Create two tables a. Table 1 - PETSALE b. Table 2 - PET

In creating the PETSALE Table, I used the following statement:

DROP TABLE PETSALE;

CREATE TABLE PETSALE (
    ID INTEGER NOT NULL,
    PET CHAR(20),
    SALEPRICE DECIMAL(6,2),
    PROFIT DECIMAL(6,2),
    SALEDATE DATE
    );

![image](https://github.com/user-attachments/assets/914786c1-ad4b-498c-a007-16ae0d1c5e11)

In creating the PET Table, I used the following statement:

DROP TABLE PET;

CREATE TABLE PET (
    ID INTEGER NOT NULL,
    ANIMAL VARCHAR(20),
    QUANTITY INTEGER
    );

![image](https://github.com/user-attachments/assets/2f9ae8b8-82a8-4794-83f3-cdc2c53c7081)

2. Insert records into the Tables

INSERT INTO PETSALE VALUES
    (1,'Cat',450.09,100.47,'2018-05-29'),
    (2,'Dog',666.66,150.76,'2018-06-01'),
    (3,'Parrot',50.00,8.9,'2018-06-04'),
    (4,'Hamster',60.60,12,'2018-06-11'),
    (5,'Goldfish',48.48,3.5,'2018-06-14');

SELECT * FROM PETSALE;

![image](https://github.com/user-attachments/assets/c31699e3-cfd4-4fea-a7e8-160da7a462d2)

INSERT INTO PET VALUES
    (1,'Cat',3),
    (2,'Dog',4),
    (3,'Hamster',2);

SELECT * FROM PET;

![image](https://github.com/user-attachments/assets/5e8ede02-0d68-423d-aa55-ced1a29d819c)

