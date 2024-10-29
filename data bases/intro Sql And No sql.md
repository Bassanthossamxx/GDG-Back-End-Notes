# **SQL and NoSql Databases**
## **Table of Contents**
- [**SQL and NoSql Databases**](#sql-and-nosql-databases)
  - [**Table of Contents**](#table-of-contents)
  - [**Introduction to Relational Databases**](#introduction-to-relational-databases)
- [**SQL Basics Guide**](#sql-basics-guide)
  - [**What is SQL?**](#what-is-sql)
  - [**Basic SQL Commands**](#basic-sql-commands)
    - [**1. SELECT - Querying Data**](#1-select---querying-data)
      - [**Basic Syntax:**](#basic-syntax)
      - [Example:](#example)
      - [Notes:](#notes)
    - [**2. INSERT - Adding New Data**](#2-insert---adding-new-data)
      - [**Basic Syntax:**](#basic-syntax-1)
      - [Example:](#example-1)
      - [Notes:](#notes-1)
  - [Ensure the **number of values** inserted matches the **number of specified columns**](#ensure-the-number-of-values-inserted-matches-the-number-of-specified-columns)
    - [**3.UPDATE - Modifying Data**](#3update---modifying-data)
      - [**Basic Syntax:**](#basic-syntax-2)
      - [Example:](#example-2)
      - [Notes:](#notes-2)
    - [**4.DELETE  - Removing Data**](#4delete----removing-data)
      - [**Basic Syntax:**](#basic-syntax-3)
      - [Example:](#example-3)
      - [Notes:](#notes-3)
    - [**5.DELETE  - JOIN - Linking Different Tables**](#5delete----join---linking-different-tables)
      - [Types of JOIN:](#types-of-join)
      - [**Basic Syntax:**](#basic-syntax-4)
      - [Example:](#example-4)
      - [Notes:](#notes-4)
- [**NoSQL Database Guide**](#nosql-database-guide)
  - [**What is NoSQL?**](#what-is-nosql)
  - [**Types of NoSQL Databases**](#types-of-nosql-databases)
    - [**Document-Oriented Databases**](#document-oriented-databases)
      - [**Basic Syntax in Document Stores (MongoDB)**](#basic-syntax-in-document-stores-mongodb)
      - [**Example of Document-Oriented Database**](#example-of-document-oriented-database)
- [**SQL vs. NoSQL: Comparison**](#sql-vs-nosql-comparison)
  - [When to Use SQL vs. NoSQL](#when-to-use-sql-vs-nosql)
  - [Conclusion](#conclusion)
- [**Additional Learning Resources**](#additional-learning-resources)
  - [**Study Tips:**](#study-tips)

---

## **Introduction to Relational Databases**

Relational databases are structured around **tables** that consist of **rows** and **columns**. This data organization allows for logical storage that is both flexible and easy to understand.
# **SQL Basics Guide**

## **What is SQL?**
**SQL** (Structured Query Language) is a programming language used to interact with relational databases. It allows you to **create, read, update, and delete** data. SQL is the foundation for many database systems, including MySQL, PostgreSQL, SQL Server, and SQLite.






---

## **Basic SQL Commands**

### **1. SELECT - Querying Data**
The `SELECT` statement is used to retrieve data from a specific table.

#### **Basic Syntax:**
```sql
SELECT column1, column2 
FROM table_name 
WHERE condition;
```

#### Example:
Suppose we have a table called employees with columns (name, department, salary), and we want to display the names and departments of employees with a salary greater than 5000

```sql
SELECT name, department 
FROM employees 
WHERE salary > 5000;
```

#### Notes:
**SELECT * FROM table_name;** to display **all columns.**

**WHERE** to specify **certain conditions.**

---

### **2. INSERT - Adding New Data**

The `INSERT` Used to add a row (new data) to a table.

#### **Basic Syntax:**
```sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

#### Example:
We want to add a new employee named "Sara" who works in the HR department with a salary of 6000
```sql
INSERT INTO employees (name, department, salary)
VALUES ('Sara', 'HR', 6000);
```

#### Notes:
Ensure the **number of values** inserted matches the **number of specified columns**
---

### **3.UPDATE - Modifying Data**

The `UPDATE ` Used to update specific data in a table

#### **Basic Syntax:**
```sql
UPDATE table_name 
SET column1 = value1, column2 = value2 
WHERE condition;
```

#### Example:
We want to increase the salaries of employees in the sales department by 10%.

sql
```sql
UPDATE employees 
SET salary = salary * 1.1 
WHERE department = 'Sales';
```

#### Notes:
Be sure to specify the ` WHERE` condition **to avoid updating all data in the table**.

---
### **4.DELETE  - Removing Data**

The `DELETE ` Used to delete specific data from a table

#### **Basic Syntax:**
```sql
DELETE FROM table_name 
WHERE condition;
```

#### Example:
We want to delete the data of the employee named "Ahmed".

```sql
DELETE FROM employees 
WHERE name = 'Ahmed';
```

#### Notes:
Be cautious when using` DELETE `, as it permanently **removes rows from the table**.

---
### **5.DELETE  - JOIN - Linking Different Tables**

The ` JOIN ` Used to combine data from different tables based on a relationship between them.
#### Types of JOIN:
1. ` INNER JOIN `
 
  *  Returns rows that have matches in both tables

1. ` LEFT JOIN `
  
  * Returns all rows from the left table, and matched rows from the right table

2. ` RIGHT JOIN `

  * Returns all rows from the right table, and matched rows from the left table

#### **Basic Syntax:**
```sql
SELECT table1.column, table2.column 
FROM table1 
JOIN table2 ON table1.common_column = table2.common_column;
```

#### Example:
Assuming there are two tables: employees and projects. We want to retrieve employee names and the projects they are working on

```sql
SELECT employees.name, projects.project_name 
FROM employees 
JOIN projects ON employees.id = projects.employee_id;

```

#### Notes:
`JOIN` helps **manage related data across different tables** and provides a comprehensive view.

---
---
# **NoSQL Database Guide**

## **What is NoSQL?**
**NoSQL** databases are non-relational and schema-less databases optimized for handling **big data** and **real-time applications**. They are known for their flexibility in data models, horizontal scalability, and efficient performance.

it can store structured, semi-structured, and unstructured data, making them ideal for web applications, IoT, and mobile apps that handle dynamic and massive datasets.

---

## **Types of NoSQL Databases**

NoSQL databases come in four primary types: `Document-oriented`, `Key-Value`,` Column-Family`, and` Graph databases`. 



### **Document-Oriented Databases**
Document-oriented databases store data in JSON-like documents. Each document is a self-contained unit of data, making it flexible for handling complex and hierarchical data structures.

- **Popular Databases**: MongoDB, CouchDB
- **Use Cases**: Content management systems, e-commerce, product catalogs, user profiles

#### **Basic Syntax in Document Stores (MongoDB)**
1. **Database Creation** (Implicit):
    - MongoDB automatically creates a database when data is inserted.
  
2. **Insert Document**:
    ```javascript
    db.collectionName.insertOne({
      "name": "Alice",
      "age": 29,
      "email": "alice@example.com",
      "location": { "city": "New York", "zip": "10001" }
    });
    ```

3. **Query Documents**:
    ```javascript
    db.collectionName.find({ "location.city": "New York" });
    ```

4. **Update Document**:
    ```javascript
    db.collectionName.updateOne(
      { "name": "Alice" },
      { $set: { "age": 30 } }
    );
    ```

5. **Delete Document**:
    ```javascript
    db.collectionName.deleteOne({ "name": "Alice" });
    ```

#### **Example of Document-Oriented Database**
Imagine a `products` collection in an e-commerce database to store product details:
```javascript
db.products.insertOne({
  "productName": "Smartphone",
  "brand": "TechBrand",
  "price": 499.99,
  "categories": ["electronics", "smartphone"],
  "inStock": true
}); 
```



# **SQL vs. NoSQL: Comparison**

| **Aspect**               | **SQL (Relational Databases)**                                 | **NoSQL (Non-Relational Databases)**                           |
|--------------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| **Structure**            | Based on fixed tables with a predefined schema                | Flexible and heterogeneous databases supporting multiple models like documents, key-value, column-family, and graph-based models |
| **Schema Flexibility**   | **Fixed** – Schema must be defined in detail before data entry | **Flexible** – Schema can be modified without updating existing data |
| **Data Integrity & Consistency** | **High** – Enforces strict data validation and relational integrity | **Flexible** – May be less consistent to prioritize performance, often using eventual consistency |
| **Scalability**          | **Vertical** – Increases system capacity by adding resources to a single server | **Horizontal** – Expands by adding multiple servers, facilitating scalability |
| **Data Types**           | Suitable for complex, diverse data connected by primary and foreign keys | Suitable for unstructured, diverse data, allowing heterogeneous data storage in a single database |
| **Transactions**         | Uses ACID (Atomicity, Consistency, Isolation, Durability) to ensure transaction reliability | Uses BASE (Basically Available, Soft state, Eventually consistent) for faster performance with less strict consistency |
| **Use Cases**            | Preferred for financial applications, accounting systems, and any system requiring high data integrity | Preferred for dynamic applications like social media, product recommendations, and IoT data |
| **Examples**             | MySQL, PostgreSQL, Oracle, SQL Server                         | MongoDB, Cassandra, Redis, Neo4j, CouchDB                       |
| **Data Relationships**   | **Complex relationships** – Managed efficiently with primary and foreign keys | **Simple or no relationships** – Preferred for applications with simple or no relational data needs |
| **Performance**          | **Relatively slower** when handling unstructured or non-relational data | **Relatively faster** when managing large volumes of unstructured data, optimized for heavy performance |
| **Development Time**     | Requires upfront schema design and table structure           | Allows for rapid development, especially with dynamic or evolving data models |
| **Community & Support**  | Established community with long-term support, suitable for enterprise systems requiring high security | Growing community with broad support, ideal for fast-growing, innovative applications |

---

## When to Use SQL vs. NoSQL

- **Use SQL Databases** if you need:
  - To manage complex, interconnected data.
  - High data integrity and strict validation.
  - To handle critical transactions, like in banking or accounting systems.
  - Detailed reporting and analysis on fairly stable data.

- **Use NoSQL Databases** if you need:
  - To manage large volumes of constantly changing data (e.g., social media user data).
  - Support for easy and quick horizontal scaling.
  - Flexibility to store diverse, unstructured data.
  - Faster performance, even with relaxed consistency.

---

## Conclusion

SQL databases are ideal for systems requiring strong data structures and complex relationships, while NoSQL is a flexible, high-performance choice for applications managing large, dynamic datasets. The decision between SQL and NoSQL depends on the project type, performance needs, and expected data growth.

# **Additional Learning Resources**

- [W3Schools SQL Tutorial](https://www.w3schools.com/sql/) : A comprehensive course for beginners explaining the basics and advanced SQL

- [SQLBolt](https://sqlbolt.com/) : An interactive site offering lessons and practical exercises to practice SQL

- [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial) : Advanced SQL lessons for those interested in analytics and reporting

- [LeetCode SQL Practice](https://leetcode.com/studyplan/top-sql-50/) : Practice common SQL questions asked in interviews
  
- [MongoDB Documentation](https://www.mongodb.com/docs/manual/) : Comprehensive guide and tutorials on MongoDB.

- [Geeks for Geeks](https://www.geeksforgeeks.org/difference-between-sql-and-nosql/) a comparison between sql and no sql databases

---

## **Study Tips:**

Try **writing queries** on direct SQL training platforms.
**Don’t just read the examples**; attempt to **modify values and conditions** to see different results.**Practice** writing each type of query using small databases (like a database for students, employees, or products) to solidify practical understanding
