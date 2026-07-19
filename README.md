# Student Admission Form (Java + JDBC + MySQL)

A simple desktop GUI application built with **Java Swing** that allows users to insert and view student records stored in a **MySQL** database, using **JDBC** for connectivity.

## Features

- Add new student records (Roll Number, Name, Age, Marks) via a clean form interface
- View all stored records in a table popup with a single click
- Input validation with clear error messages for invalid data types
- Auto-clearing form fields after successful submission

## Tech Stack

- **Language:** Java
- **GUI:** Java Swing (AWT layout, JTextField, JButton, JTable)
- **Database:** MySQL
- **Connectivity:** JDBC (`com.mysql.cj.jdbc.Driver`)
- **Utility Library:** `rs2xml` (DbUtils) for rendering ResultSet directly into a JTable

## How It Works

1. **Submit Button** — Reads form input, validates that Roll Number, Age, and Marks are numeric, then inserts the record into the `student` table using a `PreparedStatement`.
2. **Show Button** — Queries all records from the `student` table and displays them in a scrollable JTable inside a dialog.

## Database Setup

```sql
CREATE DATABASE students;

USE students;

CREATE TABLE student (
    Roll_No INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Marks INT
);
```

## Error Handling

- Catches `NumberFormatException` separately to show a user-friendly message when non-numeric input is entered in numeric fields.
- Catches general `Exception` for database connection or query issues.

## Screenshots

*(Add screenshots of the form and the Show Table popup here)*

## Future Improvements

- Add Update and Delete functionality
- Switch to a proper table layout (GridBagLayout) instead of absolute positioning
- Add form-level input validation (e.g., max marks, age range)
- Connect via a connection pool instead of creating a new connection per action

## Author

Built by Saad Naeem as part of a hands-on Java + JDBC learning project.
