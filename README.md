# TechCorp Employee Management System

Welcome to the **TechCorp Employee Management System** repository. This project was developed as a comprehensive case study to showcase advanced skills in database design, SQL querying, and data integrity management. The case study simulates a real-world scenario for "TechCorp," a mid-sized company that needs an efficient solution to manage employee data, departments, projects, salaries, and attendance.

---
## Table of Contents

- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Database Design](#database-design)
- [SQL Implementation](#sql-implementation)
- [Files Included](#files-included)
- [Usage](#usage)
- [Future Enhancements](#future-enhancements)
- [License](#license)

---
## Introduction

This repository not only serves as a demonstration of robust SQL and database design principles but also acts as a portfolio project. It highlights my capability to handle normalization, constraints, referential integrity, and complex queries in a real-life motivated scenario. Whether you are a potential employer or a fellow developer, I invite you to explore this project and gain insights into structured data management practices.

---

## Project Overview

The **Employee Management System** is centered around a series of interconnected tables designed with normalization (up to 3rd Normal Form) and strong constraints to ensure data integrity. The system manages:

- **Employee details**: Personal information, contact details, and job-related data.
- **Department & Job Titles**: Organization structure and role classifications.
- **Attendance**: Daily attendance records with defined valid statuses.
- **Salary**: Salary information along with bonus and deduction details.
- **Projects**: Project details and assignments with clear manager accountability.
- **Project Allocations**: A many-to-many mapping to allocate employees to projects while preventing duplicate assignments.

This project also demonstrates advanced SQL topics including triggers, transactions, string manipulation, and date/time functions.

---

## Database Design

For a quick glance at the complete schema, please refer to the included schema image file: 
<img src='https://github.com/RCJ360/TechCorp_Employee_Management_System/blob/main/Employee%20Management%20System_Schema.jpg' width='1000' height = '550'>

The database schema is structured into the following tables with their core constraints:

1. **Department Table**  
   - **Columns**: `DepartmentID` (Primary Key), `DepartmentName` (NOT NULL)  
   - **Goal**: Maintain unique and non-null department names.

2. **Job Title Table**  
   - **Columns**: `JobTitleID` (Primary Key), `JobTitleName` (UNIQUE, NOT NULL)  
   - **Goal**: Prevent duplicate job titles and enforce data validity.

3. **Employee Table**  
   - **Columns**: `EmployeeID` (Primary Key), `FirstName`, `LastName` (both NOT NULL), `DateOfBirth`, `Gender`, `PhoneNumber` (UNIQUE), `Email` (UNIQUE), `HireDate`, `DepartmentID`, `JobTitleID`, `ManagerID` (nullable self-referencing foreign key)  
   - **Goal**: Capture employee information with a flexible reporting structure (employees without a manager).

4. **Attendance Table**  
   - **Columns**: `AttendanceID` (Primary Key), `EmployeeID` (Foreign Key), `Date`, `Status` (must be 'Present', 'Absent', or 'Leave')  
   - **Goal**: Ensure attendance records are valid with constraint-enforced statuses.

5. **Salary Table**  
   - **Columns**: `SalaryID` (Primary Key), `EmployeeID` (Foreign Key), `BaseSalary` (NOT NULL), `Bonus` (default 0.00), `Deduction` (default 0.00), `PaymentDate`  
   - **Goal**: Accurate salary management with default values for bonus and deductions.

6. **Project Table**  
   - **Columns**: `ProjectID` (Primary Key), `ProjectName` (NOT NULL), `StartDate`, `EndDate`, `ProjectManagerID` (Foreign Key referencing Employee)  
   - **Goal**: Record project details and designate clear managerial responsibility.

7. **Project Allocation Table**  
   - **Columns**: `AllocationID` (Primary Key), `EmployeeID` (Foreign Key), `ProjectID` (Foreign Key), `AllocationDate`  
   - **Unique Constraint**: Combination of `EmployeeID` and `ProjectID` must be unique  
   - **Goal**: Prevent multiple allocations of the same employee to a single project.
   
---

## SQL Implementation

The repository includes key files:
 1. Schema Creation & Data Insertion
    - Defines tables with primary keys, foreign keys, and integrity constraints.
    - Inserts sample data for validation.
 2. Queries & Function Creation
    - Retrieves employee, project, salary, attendance data.
    - Demonstrates advanced SQL functions.

---

## Files Included
1. Schema Creation Data Insertion.sql
   - Contains SQL code to create tables with normalization, constraints, and initial data insertion queries.
2. SQL Queries Function Creation.sql
   - Features advanced SQL queries, function creation, and data retrieval scenarios based on project requirements.
3. Employee Management System_Schema.jpg
   - An image of the database schema illustrating table relationships and constraints.

---

## Usage
To get started:
1. Clone the Repository:
   https://github.com/RCJ360/TechCorp_Employee_Management_System.git
   
   cd TechCorp-Employee-Management-System
3. Review and Run SQL Scripts:
   - Execute the schema creation script in your preferred SQL environment.
   - Follow up with data insertion and query scripts to see the system in action.
3. View the Schema Diagram:
   - Open Employee Management System_Schema.jpg to understand the table relationships visually.

---
## Future Enhancements
Potential future improvements include:
 - Implementing stored procedures and triggers for automated data validation.
 - Expanding the project with a user interface for data entry and reporting.
 - Integrating advanced transaction management and error handling for increased robustness.

---

## License
This project is licensed under the MIT License.

Thank you for exploring the TechCorp Employee Management System. I welcome feedback and suggestions for future enhancements!
