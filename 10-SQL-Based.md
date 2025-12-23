# SQL Interview Sheet

# Table of Contents

- [1. What is SQL?](#1-what-is-sql)
- [2. What are tables and rows in SQL?](#2-what-are-tables-and-rows-in-sql)
- [3. What is a primary key?](#3-what-is-a-primary-key)
- [4. What is a foreign key?](#4-what-is-a-foreign-key)
- [5. Difference between Primary Key and Unique Key](#5-difference-between-primary-key-and-unique-key)
- [6. What is a SELECT statement?](#6-what-is-a-select-statement)
- [7. Difference between WHERE and HAVING](#7-difference-between-where-and-having)
- [8. What is GROUP BY?](#8-what-is-group-by)
- [9. What are aggregate functions?](#9-what-are-aggregate-functions)
- [10. Difference between DELETE, TRUNCATE, and DROP](#10-difference-between-delete-truncate-and-drop)
- [11. What is a JOIN?](#11-what-is-a-join)
- [12. What is a subquery?](#12-what-is-a-subquery)
- [13. Difference between subquery and join](#13-difference-between-subquery-and-join)
- [14. What is IN and EXISTS?](#14-what-is-in-and-exists)
- [15. What is UNION and UNION ALL?](#15-what-is-union-and-union-all)
- [16. What is normalization?](#16-what-is-normalization)
- [17. What is denormalization?](#17-what-is-denormalization)
- [18. What is an index?](#18-what-is-an-index)
- [19. What is ACID property?](#19-what-is-acid-property)


## 1. What is SQL?
- SQL stands for **Structured Query Language**.
- It is used to **store, manage, and retrieve data** from relational databases.
- SQL allows us to **query data**, **insert records**, **update data**, and **delete records** from tables.

## 2. What are tables and rows in SQL?
- A **table** is a **structured collection of data** stored in **rows and columns**.
- **Rows** represent **individual records** stored in the table.
- **Columns** represent **schema or attributes** of the table.

## 3. What is a primary key?
- A **primary key** is a **column** that **uniquely identifies each record** in a table.
- It contains **unique** and **Not NULL** value.

## 4. What is a foreign key?
- A **foreign key** is a **column** that **creates a relationship** between two tables.
- It **refers to the primary key** of another table.

## 5. Difference between Primary Key and Unique Key
| Feature | Primary Key | Unique Key |
|---------|--------------|------------|
| NULLs allowed | **No Null value allow** | **One NULL allowed** |
| Number of columns | **Only one in table** | **Multiple allowed** |
| Purpose | **Identify records** | **Ensure uniqueness** |

## 6. What is a SELECT statement?
- The **SELECT** statement is used to **retrieve data** from a database table.
- It can **fetch specific columns** or **all columns** from **one or more tables**.

## 7. Difference between WHERE and HAVING
- **WHERE**: Used to **filter rows** **before grouping**; works on **individual rows**.
- **HAVING**: Used to **filter groups** **after aggregation**; works on **grouped data**.
- 
| Conditions | LIKE, IN, BETWEEN, comparison operators (<, >, =, !=, <=, >=), logical operators (AND, OR, NOT) | Conditions on aggregated data 

## 8. What is GROUP BY?
- **GROUP BY** is used to **group rows** that have **the same values** in a specific column.
- Mainly used with **aggregate functions** like **COUNT**, **SUM**, and **AVG**.

## 9. What are aggregate functions?
Aggregate functions perform **calculations on multiple rows** or **Group data** and **return a single value**.

| Function | Description |
|------------|--------------|
| **COUNT** | Counts rows |
| **SUM** | Adds values |
| **AVG** | Calculates average |
| **MIN** | Finds minimum value |
| **MAX** | Finds maximum value |

## 10. Difference between DELETE, TRUNCATE, and DROP
| Operation | Description | Rollback | Notes |
|------------|--------------|----------|--------|
| **DELETE** | Removes selected rows | Yes | Can be rolled back |
| **TRUNCATE** | Removes all rows | No | Keeps table structure |
| **DROP** | Removes entire table | No | Deletes table and structure |

## 11. What is a JOIN?
- **JOIN** is used to **combine data** from **two or more tables** based on **related columns**.
- Types of **JOINs**:
  - **INNER JOIN**: Returns **only matches row** from  both tables.
  - **LEFT JOIN**: Returns **all rows from the left table** and matching rows from the right table.
  - **SELF JOIN**: Joins a table **with itself**.
  - **CROSS JOIN**: Returns the **Cartesian product** of both tables.

## 12. What is a subquery?
- A **subquery** is a **query within another query**.
- Used to **get first**, then use the result in the **main query**.

## 13. Difference between subquery and join

| Aspect | Subquery | JOIN |
|---------|------------|-------|
| Meaning | Query inside another query | Combines data from multiple tables |
| Execution | Inner query runs first | Tables are joined and processed together |
| Performance | Can be slower for large data | Usually faster and optimized |
| Result | Returns a value or list | Returns combined rows |

## 14. What is IN and EXISTS?
- **IN**: Checks if a **value matches any** value in a **list or subquery**.
- **EXISTS**: Checks whether a **subquery returns at least one** **matching row**; based on which it returns **true/false**.

## 15. What is UNION and UNION ALL?
- **UNION**: Combines results of two or more **SELECT queries** and **removes duplicates**.
- **UNION ALL**: Combines results **including duplicates**.

## 16. What is normalization?
- Normalization is a process of **organizing data** to:
  - **Reduce redundancy**
  - **Improve data integrity**
  - **Ensure logical data dependencies**

### Normal Forms:
- **1NF**: Atomic values in each column, no multiple values.
- **2NF**: In 1NF and **no partial dependency**.
- **3NF**: No transitive dependency.

## 17. What is denormalization?
- The **process of intentionally combining normalized tables** to **improve read performance**.
- Done to:
  - Improve read speed
  - Reduce complex joins
  - Speed up queries in large databases

## 18. What is an index?
- An **index** improves **data retrieval speed** from a table.

### Pros and Cons:
| Pros | Cons |
|--------|--------|
| Faster data retrieval | Slower write operations |
| Improves filtering, joining, sorting | Extra storage required |

## 19. What is ACID property?
- Ensures **transactions** are **safe, correct, and reliable**:
  - **Atomicity**: All-or-nothing transactions.
  - **Consistency**: Database remains in a **valid state**.
  - **Isolation**: Transactions **do not affect each other**.
  - **Durability**: Changes **persist** even after system failure.

---

Feel free to copy and use this markdown for your GitHub documentation!
