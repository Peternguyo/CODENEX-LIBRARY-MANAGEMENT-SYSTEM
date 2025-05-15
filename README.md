# CODENEX-LIBRARY-MANAGEMENT-SYSTEM
This project is a MySQL-based relational database for managing a library. It supports storing book data, author details, member information, staff, and borrowing records.

# Library Management System

## 📚 Description
This project is a MySQL-based relational database for managing a library. It supports storing book data, author details, member information, staff, and borrowing records.

## ⚙️ How to Set Up
1. Open MySQL Workbench or your SQL editor.
2. Run the `library_management.sql` file to create the database and tables.

## 🧱 Features
- Books linked to authors.
- Members borrowing multiple books.
- Borrowing records handled by staff.
- Includes foreign keys and constraints.

## Walk through on how to build this Database Management System using MySQL step-by-step. 
✅ Step 1: Choose a library use case
We'll use a Library Management System as an example because it's simple, common, and includes a variety of relationships like:

Books

Members

Borrowing records

Authors

Staff

✅ Step 2: Design the Entity-Relationship Diagram (ERD)
Here are the main entities and relationships:

<!-- Entities: -->
Books (BookID, Title, ISBN, AuthorID, Publisher, Category, Copies)

Authors (AuthorID, Name)

Members (MemberID, Name, Email, Phone)

Staff (StaffID, Name, Role)

Borrowing (BorrowID, BookID, MemberID, BorrowDate, ReturnDate, StaffID)

<!-- Relationships: -->
A book has one author (1-M)

A member can borrow many books (1-M)

A borrowing record is handled by one staff member (1-M)

A book can be borrowed many times (1-M)

<!-- writing the code --> 

<!-- -- Create database
CREATE DATABASE IF NOT EXISTS LibraryDB;
USE LibraryDB;

-- 1. Authors Table
CREATE TABLE Authors (
    AuthorID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL
);

-- 2. Books Table
CREATE TABLE Books (
    BookID INT AUTO_INCREMENT PRIMARY KEY,
    Title VARCHAR(255) NOT NULL,
    ISBN VARCHAR(20) UNIQUE NOT NULL,
    AuthorID INT,
    Publisher VARCHAR(100),
    Category VARCHAR(50),
    Copies INT DEFAULT 1,
    FOREIGN KEY (AuthorID) REFERENCES Authors(AuthorID)
);

-- 3. Members Table
CREATE TABLE Members (
    MemberID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL,
    Phone VARCHAR(15) UNIQUE
);

-- 4. Staff Table
CREATE TABLE Staff (
    StaffID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    Role VARCHAR(50) NOT NULL
);

-- 5. Borrowing Table
CREATE TABLE Borrowing (
    BorrowID INT AUTO_INCREMENT PRIMARY KEY,
    BookID INT,
    MemberID INT,
    BorrowDate DATE NOT NULL,
    ReturnDate DATE,
    StaffID INT,
    FOREIGN KEY (BookID) REFERENCES Books(BookID),
    FOREIGN KEY (MemberID) REFERENCES Members(MemberID),
    FOREIGN KEY (StaffID) REFERENCES Staff(StaffID)
); -->

## 🔗 ERD
![screenshot of the ERD](<Library management system  ERD-1.png>)
