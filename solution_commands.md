# Solution
- This document contains the commands used to create the database seen in the ERD
## Creating the database
```
CREATE DATABASE bookstore; 
```
## Creating user_table table
```
CREATE TABLE user_table(  
users_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,  
first_name VARCHAR(20),  
last_name VARCHAR(20),  
email VARCHAR(30),  
phone_no CHAR(11) 
); 
```
## Creating Ebooks table
```
CREATE TABLE Ebooks(  
ebook_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,  
users_id INT FOREIGN KEY REFERENCES user_table(users_id),  
title VARCHAR(50),  
book_location VARCHAR(6),  
release_date DATE, 
price DECIMAL(5,2) 
); 
```
## Creating Booking table
```
CREATE TABLE Booking(  
booking_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,  
users_id INT FOREIGN KEY REFERENCES user_table(users_id),  
purchase_date DATE 
); 
```
## Creating linking table between Booking and Ebooks
```
CREATE TABLE book_transaction(  
transation_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,
booking_id INT NOT NULL FOREIGN KEY REFERENCES user_table(users_id), 
users_id  INT NOT NULL FOREIGN KEY REFERENCES user_table(users_id)
); 
```
