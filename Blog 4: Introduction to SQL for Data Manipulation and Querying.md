You're welcome! Let's continue with the fourth blog in the series, which will focus on SQL fundamentals for data manipulation and querying.

---

# Blog 4: Introduction to SQL for Data Manipulation and Querying

## Introduction

With a solid understanding of Python’s data types and structures under your belt, it's time to add another essential tool to your data science toolkit: SQL, or Structured Query Language. SQL is the standard language for relational database management systems and is fundamental for data manipulation and retrieval. In this blog, we'll cover the basics of SQL, focusing primarily on data manipulation and querying.

## What is SQL?

SQL stands for Structured Query Language. It is a domain-specific language used for managing and manipulating relational databases. While Python is excellent for data analysis, SQL excels at data storage and retrieval, making them complementary tools in your data science arsenal.

## SQL Data Types

Just like in Python, understanding data types in SQL is crucial. Some common SQL data types are:

### Numeric Types

- **INT**: For integers.
  
- **FLOAT**: For floating-point numbers.
  
- **DECIMAL**: For exact numeric values.

### Text Types

- **CHAR**: Fixed-length character string.
  
- **VARCHAR**: Variable-length character string.
  
- **TEXT**: For holding large bodies of text.

### Date Types

- **DATE**: For date values.
  
- **TIME**: For time values.
  
- **DATETIME**: For both date and time.

## Basic SQL Commands

Let's explore some basic SQL commands that are vital for data manipulation and querying.

### Data Definition Language (DDL)

#### CREATE TABLE
- Used to create a new table.
  
  ```sql
  CREATE TABLE Employees (
      ID INT,
      Name VARCHAR(50),
      Age INT
  );
  ```

#### DROP TABLE
- Used to delete an existing table.
  
  ```sql
  DROP TABLE Employees;
  ```

### Data Manipulation Language (DML)

#### INSERT INTO
- Inserts new records into a table.
  
  ```sql
  INSERT INTO Employees (ID, Name, Age) VALUES (1, 'John', 30);
  ```

#### UPDATE
- Modifies existing records.
  
  ```sql
  UPDATE Employees SET Age = 31 WHERE ID = 1;
  ```

#### DELETE
- Deletes records from a table.
  
  ```sql
  DELETE FROM Employees WHERE ID = 1;
  ```

### Querying Data

#### SELECT
- Retrieves data from one or more tables.
  
  ```sql
  SELECT * FROM Employees WHERE Age > 25;
  ```

#### JOIN
- Combines rows from two or more tables based on a related column.
  
  ```sql
  SELECT Employees.Name, Orders.OrderID
  FROM Employees
  JOIN Orders ON Employees.ID = Orders.EmployeeID;
  ```

## SQL in Python

You can execute SQL queries in Python using libraries like SQLite for local database management or SQLAlchemy for more robust, production-level databases.

```python
import sqlite3

# Connect to SQLite database
conn = sqlite3.connect('employees.db')

# Create a table
conn.execute("""
CREATE TABLE Employees (
    ID INT PRIMARY KEY,
    Name TEXT,
    Age INT
);
""")

# Insert data
conn.execute("INSERT INTO Employees (ID, Name, Age) VALUES (1, 'John', 30);")

# Query data
cursor = conn.execute("SELECT * FROM Employees WHERE Age > 25;")
for row in cursor:
    print(row)

# Close the connection
conn.close()
```

## Conclusion

SQL is indispensable for data manipulation and querying in a relational database. Together with Python, it forms the backbone of most data science operations. Understanding both allows you to be incredibly versatile in handling, analyzing, and storing data. In the next blog, we will delve deeper into advanced SQL queries and techniques to give you more querying superpowers.

---

I hope this blog gives you a good introduction to SQL and its importance in the realm of data science. Stay tuned for the next installment, where we'll explore more advanced SQL queries and techniques!
