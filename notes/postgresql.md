# PostgreSQL (or Postgres)

## Table of Contents
- [Relational Databases](#relational-databases)
- [PostgreSQL](#postgresql)
- [Scaling Databases](#scaling-databases)
  - [Database Indexes](#database-indexes)
  - [Data Replication](#data-replication)
  - [Sharding Strategies](#sharding-strategies)
  - [CAP Theorem](#cap-theorem)
- [More About Databases](#more-about-databases)
  - [ORMs](#orms)
  - [ACID](#acid)
  - [Transactions](#transactions)
  - [N+1 Problem](#n1-problem)
  - [Normalization](#normalization)
  - [Failure Modes](#failure-modes)
  - [Profiling Performance](#profiling-performance)

## Relational Databases
- A relational database stores and provides access to data points that are related to one another in a series of tables
- Interconnections betwen the tables are specified as foreign keys
- A foreign key is a unique reference from one row in a relational table to another row in a table, which can be the same table but is most commonly a different table

---

- Relational databases organize data into rows and columns that together form a table where the data points are related to each other
- Data is typically structured across multiple tables, which can be joined together via a primary key or a foreign key
- These unique identifiers demonstrate the different relationships that exist between tables, and these relationships are usually illustrated through different types of data models
- Relational databases are typically associated with transactional databases, which execute commands (i.e. transactions) collectively
- Transactions have specific properties that are represented by the acronym `ACID`:
  - **Atomicity:** All changes to data are performed as if they are a single operation
  - That is, all the changes are performed, or none of them are
  - **Consistency:** Data remains in a consistent state form state to finish, reinforcing data integrity
  - **Isolation:** The intermediate state of a transaction is not visible to other transactions, and as a result, transactions that run concurrently appear to be serialized
  - **Durability:** After the successful completion of a transaction, changes to data persist and are not undone, even in the event of a system failure
- These properties enable reliable transaction processing
- A relational database management system (RDBMS) is a more specific reference to the underlying database software that enables users to maintain a relational database
- RDBMS allow users to create, update, insert, or delete data in the system, and tehy provide:
  - Data structure
  - Multi-user access
  - Priviliege control
  - Network access
- An example of a relational database management system is PostgreSQL

---

- Tables are made up of rows, also known as records or tuples, and columns, which are also called attributes or fields
- The term “relational” comes from the fact that these tables can be related to one another through keys and relationships
- Key concepts of relational databases:
  - **Table:** A collection of data organized into rows and columns
  - Each table has a unique name and represents a specific object or activity in the database
  - **Row:** A single entry in a table that contains a specific instance of data
  - Each row in a table has the same columns and represents a single record
  - **Column:** A data field in a table that represents a specific attribute of the data
  - Columns have a unique name and a specific data type
  - **Primary Key:** A column (or a set of columns) in a table that uniquely identifies each row
  - No two rows can have the same primary key value
  - **Foreign Key:** A column (or a set of columns) in a table that refers to the primary key of the same or another table
  - Foreign keys are used to establish relationships between tables
- One of the main advantages of a relational database is its ability to represent relationships between tables as one-to-one, one-to-many, or many-to-many relationships
  - **One-to-One:** A relationship where a row in one table has a single corresponding row in another table, e.g. a person could have a single passport, and a passport can only belong to one person
  - **One-to-Many:** A relationship where a row in one table can have multiple corresponding rows in another table, e.g. a customer can have multiple orders, but an order can only belong to one customer
  - **Many-to-Many:** A relationship where multiple rows in one table can have multiple corresponding rows in another table, e.g. a student can enroll in multiple courses, and a course can have multiple students enrolled
  - To represent a many-to-many relationship, a third table, called a _junction table_ or _associative table_, is needed
- Relationships allow for efficient querying and manipulation of related data across multiple tables
- Relational databases offer several advantages in terms of efficiency, flexibility, and data integrity:
  - **Structured data:** The table-based organization of relational databases makes them well-suited for handling structured data, which has a consistent structure and can be easily mapped to the columns and rows of a table
  - **Data integrity:** Relational databases use primary and foreign keys to maintain consistent relationships between related data, reducing the chances of data inconsistency and redundancy
  - **Scalability:** Relational databases can handle large amounts of structured data and can be scaled to accommodate growing data requirements
  - **Querying:** The SQL (Structured Query Language) is used for querying, updating, and managing relational databases, providing a powerful and standardized way to access and manipulate the data
 
---

- Benefits of RDBMS:
  - **Structured data:** RDBMS allows data storage in a structured way, using rows and columns in tables
  - This makes it easy to manipulate the data using SQL (Structured Query Language), ensuring efficient and flexible usage
  - **ACID properties:** ACID stands for Atomicity, Consistency, Isolation, and Durability
  - These properties ensure reliable and safe data manipulation in a RDBMS, making it suitable for mission-critical applications
  - **Normalization:** RDBMS supports data normalization, a process that organizes data in a way that reduces data redundancy and improves data integrity
  - **Scalability:** RDBMSs generally provide good scalability options, allowing for the addition of more storage or computational resources as the data and workload grow
  - **Data integrity:** RDBMS provides mechanisms like constraints, primary keys, and foreign keys to enforce data integrity and consistency, ensuring that the data is accurate and reliable
  - **Security:** RDBMSs offer various security features such as user authentication, access control, and data encryption to protect sensitive data
- Limitations of RDBMS:
  - **Complexity:** Setting up and managing an RDBMS can be complex, especially for large applications
  - It requires technical knowledge and skills to manage, tune, and optimize the database
  - **Cost:** RDBMSs can be expensive, both in terms of licensing fees and the computational and storage resources they require
  - **Fixed schema:** RDBMS follows a rigid schema for data organization, which means any changes to the schema can be time-consuming and complicated
  - **Handling of unstructured data:** RDBMSs are not suitable for handling unstructured data like multimedia files, social media posts, and sensor data, as their relational structure is optimized for structured data
  - **Horizontal scalability:** RDBMSs are not as easily horizontally scalable as NoSQL databases
  - Scaling horizontally, which involves adding more machines to the system, can be challenging in terms of cost and complexity

## PostgreSQL
- PostgreSQL (or Postgres) is a free and open-source object-relational database management system (ORDBMS) emphasizing robustness, extensibility, and SQL compliance
- Key features of PostgreSQL include:
  - **ACID compliance:** Fully ACID-compliant, ensuring the reliability and data integrity of the database transactions
  - **Extensbility:** Allows users to define their data types, operators, functions, and more, which makes it highly customizable and adaptable to various use cases
  - **Concurrency control:** PostgreSQL efficiently handles concurrent queries without lock contention through its Multi-Version Concurrency Control (MVCC) mechanism
  - **Full-text search:** Provides powerful text searching capabilities, including text indexing and various search functions
  - **Spatial database capabilities:** PostgreSQL offers support for geographic objects and spatial querying through the PostGIS extension, making it ideal for GIS applications
  - **High availability:** PostgreSQL has built-in support for replication, allowing for high availability and fault tolerance
- Benefits of PostgreSQL include:
  - Its open-source and community-driven approach, which means that it is free for use and is continuously worked on and improved by a dedicated group of developers
  - It is highly scalable, making it suitable for both small-scale projects and large-scale enterprise applications
  - It is platform-independent, which means it can run on various operating systems like Windows, Linux, and macOS
- PostgreSQL can be used for a wide variety of applications, thanks to its versatility and extensibility
- Use cases for PostgreSQL include:
  - Web applications
  - Geographic Information Systems (GIS)
  - Data warehousing and analytics
  - Financial and banking systems
  - Content management systems (CMS)
  - Enterprise Resource Planning (ERP) systems

---

-

---

### Relating Records with Joins

- Table order betwen `FROM` and `JOIN` frequently makes a difference
- We must give context if column names collide
- Tables can be renamed using teh `AS` keyword
- There are multiple kinds of joins: inner join, left outer join, right outer join, full join

#### Inner Join

- Whenever you're using the keyword `JOIN` by itself in a query, it's an inner join by default
- You can use the keyword `JOIN` or `INNER JOIN`
- Example:

```sql
SELECT url, username
FROM photos
INNER JOIN users ON users.id = photos.user_id;
```

- `INNER JOIN` merges two tables together and drops rows from the overall result set whenever there are values or rows inside these tables that don't match up to a row in the other table
- In other words, with `INNER JOIN`, only rows that match up to a row in the other table are kept

#### Left Outer Join (or Left Join)

- Whenever you're using the keyword `LEFT JOIN`, only the values or rows inside the "second" or "right" table don't match up to a row in the "first" or "left" table are dropped from the overall result set
- The rows from the "first" or "left" table are always kept and the row the "second" or "right" table are backfilled/filled in with `NULL`
- Example:

```sql
SELECT url, username
FROM photos
LEFT JOIN users ON users.id = photos.user_id;
```

#### Right Outer Join (or Right Join)

- Essentially the exact opposite of a left outer join
- Whenever you're using the keyword `RIGHT JOIN`, only the values or rows inside the "first" or "left" table don't match up to a row in the "second" or "right" table are dropped from the overall result set
- The rows from the "second" or "right" table are always kept and the row the "first" or "left" table are backfilled/filled in with `NULL`
- Example:

```sql
SELECT url, username
FROM photos
RIGHT JOIN users ON users.id = photos.user_id;
```

#### Full Join

- `FULL JOIN` returns "everything"
- First it will try to correctly match the rows from the left and the right table
- In addition, rows from the "second" or "right" table are always kept and the row the "first" or "left" table are backfilled/filled in with `NULL` as well as rows from the "first" or "left" table are backfilled/filled in with `NULL`
- Essentially, correct rows are matched up and the overall result set is expanded with distinct left and right outer join results

### Aggregation of Records
### Working with Large Datasets
### Sorting Records
### Unions and Intersections with Sets
### Assembling Queries with SubQueries
### Selecting Distinct Records
### Utility Operators, Keywords, and Functions

## Scaling databases

### Database Indexes
### Data Replication
### Sharding Strategies
### CAP Theorem

## More About Databases

### ORMs
### ACID
### Transactions
### N+1 Problem
### Normalization
### Failure Modes
### Profiling Performance

## Credits

- https://roadmap.sh/backend
- https://www.ibm.com/topics/relational-databases
- https://roadmap.sh/postgresql-dba
