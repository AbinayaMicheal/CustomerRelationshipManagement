# Customer Relationship Management (CRM) Project

## Overview

This project is a Customer Relationship Management (CRM) system designed to manage and analyze customer interactions and data throughout the customer lifecycle. The main goal is to improve business relationships with customers, assist in customer retention, and drive sales growth. The system includes features for managing customer data, employee data, product inventory, orders, and customer feedback.

## Database Schema

The CRM system uses a MySQL database to store information across several tables. Below is a description of each table and its attributes:

### Tables

#### 1. Customers
Stores information about the customers.

- **CustomerID**: `int(11)` - Primary Key, Auto Increment
- **FirstName**: `varchar(50)` - Customer's first name
- **LastName**: `varchar(50)` - Customer's last name
- **Email**: `varchar(100)` - Unique email address
- **Phone**: `varchar(20)` - Phone number
- **Address**: `varchar(255)` - Street address
- **City**: `varchar(50)` - City
- **State**: `varchar(50)` - State
- **ZipCode**: `varchar(10)` - Zip code
- **Country**: `varchar(50)` - Country
- **CreatedAt**: `timestamp` - Record creation timestamp, default to current timestamp

#### 2. Products
Stores information about the products.

- **ProductID**: `int(11)` - Primary Key, Auto Increment
- **ProductName**: `varchar(100)` - Name of the product
- **Description**: `text` - Description of the product
- **Price**: `decimal(10,2)` - Price of the product
- **Stock**: `int(11)` - Stock quantity, default to 0
- **CreatedAt**: `timestamp` - Record creation timestamp, default to current timestamp

#### 3. Employees
Stores information about the employees.

- **EmployeeID**: `int(11)` - Primary Key, Auto Increment
- **FirstName**: `varchar(50)` - Employee's first name
- **LastName**: `varchar(50)` - Employee's last name
- **Email**: `varchar(100)` - Unique email address
- **Phone**: `varchar(20)` - Phone number
- **Position**: `varchar(50)` - Job position
- **Department**: `varchar(50)` - Department
- **HireDate**: `date` - Date of hire
- **CreatedAt**: `timestamp` - Record creation timestamp, default to current timestamp

#### 4. Orders
Stores information about customer orders.

- **OrderID**: `int(11)` - Primary Key, Auto Increment
- **CustomerID**: `int(11)` - Foreign Key referencing Customers
- **OrderDate**: `timestamp` - Date of the order, default to current timestamp
- **TotalAmount**: `decimal(10,2)` - Total amount of the order
- **Status**: `varchar(50)` - Order status, default to 'Pending'

#### 5. CustomerFeedback
Stores customer feedback related to orders.

- **FeedbackID**: `int(11)` - Primary Key, Auto Increment
- **CustomerID**: `int(11)` - Foreign Key referencing Customers
- **OrderID**: `int(11)` - Foreign Key referencing Orders
- **Rating**: `int(11)` - Rating given by the customer
- **Comments**: `text` - Comments from the customer
- **CreatedAt**: `timestamp` - Record creation timestamp, default to current timestamp

## Relationships

- **Customers** and **Orders**: One-to-many relationship (one customer can place many orders).
- **Orders** and **CustomerFeedback**: One-to-one relationship (one order can have one feedback).
- **Customers** and **CustomerFeedback**: One-to-many relationship (one customer can give many feedbacks).

