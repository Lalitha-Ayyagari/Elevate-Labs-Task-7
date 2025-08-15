# Elevate-Labs-Task-7
Employee Database Application
Overview
This is a Java-based application that uses JDBC to connect to a MySQL database and perform CRUD (Create, Read, Update, Delete) operations on an Employee table. The application provides a console-based interface for managing employee records.
Prerequisites

Java Development Kit (JDK): Version 8 or higher
MySQL: Installed and running
MySQL Connector/J: JDBC driver for MySQL
IDE: VS Code or any Java-compatible IDE
MySQL Server: Running on localhost:3306

Setup Instructions

Install MySQL:

Download and install MySQL from https://dev.mysql.com/downloads/
Ensure the MySQL server is running


Download MySQL Connector/J:

Get the MySQL JDBC driver from https://dev.mysql.com/downloads/connector/j/
Add the .jar file to your project's classpath in VS Code


Configure Database Connection:

Open EmployeeDatabaseApp.java
Update the PASSWORD constant with your MySQL root password:private static final String PASSWORD = "your_password";


Optionally, modify the URL and USER if your MySQL setup uses a different host, port, or username


Project Setup in VS Code:

Create a new Java project
Place EmployeeDatabaseApp.java in the src folder
Add the MySQL Connector/J .jar to the project's referenced libraries



Running the Application

Compile and run EmployeeDatabaseApp.java in VS Code
The application will:
Create a database named employee_db (if it doesn't exist)
Create an employees table with columns: id, first_name, last_name, email, salary


Use the console menu to:
Add Employee: Enter details to create a new employee record
View All Employees: Display all employee records
Update Employee: Modify an existing employee by ID
Delete Employee: Remove an employee by ID
Exit: Close the application



Using PostgreSQL (Optional)
To use PostgreSQL instead of MySQL:

Install PostgreSQL and ensure the server is running
Download the PostgreSQL JDBC driver from https://jdbc.postgresql.org/
Modify EmployeeDatabaseApp.java:
Update the driver: Class.forName("org.postgresql.Driver");
Update the URL: jdbc:postgresql://localhost:5432/employee_db
Modify the table creation SQL in createDatabaseAndTable:String createTableSQL = "CREATE TABLE IF NOT EXISTS employees (" +
        "id SERIAL PRIMARY KEY," +
        "first_name VARCHAR(50) NOT NULL," +
        "last_name VARCHAR(50) NOT NULL," +
        "email VARCHAR(100) UNIQUE NOT NULL," +
        "salary DOUBLE PRECISION NOT NULL)";




Update the database credentials (USER and PASSWORD) as needed

Troubleshooting

Driver Not Found: Ensure the MySQL/PostgreSQL JDBC driver is correctly added to the classpath
Connection Errors: Verify MySQL/PostgreSQL server is running and credentials are correct
SQL Errors: Check the SQL syntax and ensure the database server supports the queries

Notes

The application uses PreparedStatement to prevent SQL injection
All database operations are wrapped in try-with-resources for proper resource management
The employee table is created automatically on first run
