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

# Task A: Creating Tables

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


# Task B: ALTER using ADD COLUMN

1. Add a new QUANTITY column to the PETSALE table and show the altered table.

To add a new column called Quantity, I used the statement below:

ALTER TABLE PETSALE
ADD COLUMN QUANTITY INTEGER;

SELECT * FROM PETSALE;

![image](https://github.com/user-attachments/assets/6c44d020-d847-477c-9aaf-547718a60302)

UPDATE PETSALE SET QUANTITY = 9 WHERE ID = 1;
UPDATE PETSALE SET QUANTITY = 3 WHERE ID = 2;
UPDATE PETSALE SET QUANTITY = 2 WHERE ID = 3;
UPDATE PETSALE SET QUANTITY = 6 WHERE ID = 4;
UPDATE PETSALE SET QUANTITY = 24 WHERE ID = 5;

SELECT * FROM PETSALE;

![image](https://github.com/user-attachments/assets/e4693b3d-cffc-4a78-aa87-c9436095bfcf)

# Task c: ALTER using DROP COLUMN

To delete the PROFIT column from the PETSALE table and show the altered table, I used the following statement:

ALTER TABLE PETSALE
DROP COLUMN PROFIT;

SELECT * FROM PETSALE;

![image](https://github.com/user-attachments/assets/0d0b1b9c-2b37-411b-982b-1b3d68c52355)

# Task D: ALTER using ALTER COLUMN

To change the data type to VARCHAR(20) type of the column PET of the table PETSALE and show the altered table, I used the following statement:

ALTER TABLE PETSALE ALTER COLUMN PET TYPE VARCHAR(20);

SELECT * FROM PETSALE;

![image](https://github.com/user-attachments/assets/95c99d34-2016-4209-98e1-0b545331c365)

# Task E: ALTER using RENAME COLUMN

To rename the column PET to ANIMAL of the PETSALE table and show the altered table, I used the folowing statement:

-- Rename the column from PET to ANIMAL
ALTER TABLE PETSALE RENAME COLUMN PET TO ANIMAL;

-- Change the column type to varchar(20)
ALTER TABLE PETSALE ALTER COLUMN ANIMAL TYPE VARCHAR(20);

-- Select all data from the table
SELECT * FROM PETSALE;

![image](https://github.com/user-attachments/assets/4831a878-3969-493e-85c7-8971c68ebfcc)


