# 4. PostgreSQL

## 💡 What is PostgreSQL?

**PostgreSQL** is an open-source **relational database management system (RDBMS)**.

It uses SQL and provides features such as:

* Tables
* Relationships
* Foreign keys
* Constraints
* Transactions
* Indexes
* Views
* Triggers
* Functions
* Subqueries
* JSON/JSONB
* Extensions

PostgreSQL is widely used for web applications, APIs, analytics systems, and many other applications that require structured and reliable data storage.

---

## 4.1 What is SQL?

**SQL** stands for **Structured Query Language**.

SQL is a **declarative language** used to define, query, manipulate, and manage data in relational databases.

Example:

```sql
SELECT *
FROM users
WHERE age > 18;
```

SQL describes **what data you want**, rather than specifying every step the database must take to retrieve it.

---

## 4.2 Relational Concepts

### 4.2.1 Tables

Tables organize data into **rows and columns**.

```text
USERS

user_id | name    | email
--------|---------|----------------
1       | Othmane | othmane@email.com
2       | Ahmed   | ahmed@email.com
```

### 4.2.2 Primary Keys

A **primary key** uniquely identifies each row in a table.

```sql
user_id SERIAL PRIMARY KEY
```

Important properties:

* Unique
* Cannot be `NULL`
* Identifies a row

> ⚠️ A primary key does not have to be auto-incrementing.

UUIDs, for example, can also be primary keys.

---

### 4.2.3 Foreign Keys

A **foreign key** creates a relationship between tables by referencing a key in another table.

Example:

```text
users
---------
user_id PK

orders
---------
order_id PK
user_id FK
```

```text
users.user_id
      ↑
      │
orders.user_id
```

This allows the database to enforce **referential integrity**.

---

### 4.2.4 Relationships

Relationships describe how records in different tables are connected.

#### One-to-One

One record is related to one record.

```text
User ─── Profile
  1          1
```

#### One-to-Many

One record can be related to many records.

```text
User
 │
 ├── Order
 ├── Order
 └── Order
```

#### Many-to-Many

Many records can relate to many records.

Usually represented using a **junction/association table**.

```text
Orders
   │
   │
Order_Items
   │
   │
Books
```

---

## 4.3 SQL Fundamentals

### 📚 Topics

#### Data Retrieval

```text
SELECT
FROM
WHERE
ORDER BY
LIMIT
OFFSET
```

#### Data Modification

```text
INSERT
UPDATE
DELETE
```

#### Aggregation

```text
COUNT
SUM
AVG
MIN
MAX
```

#### Grouping

```text
GROUP BY
HAVING
```

#### Relationships

```text
JOIN
LEFT JOIN
Other JOIN types
```

#### Advanced Queries

```text
Subqueries
```

### 🧠 Mental Model

```text
SELECT
  ↓
What do I want?

FROM
  ↓
Where does the data come from?

WHERE
  ↓
Which rows do I want?

GROUP BY
  ↓
How should I group the rows?

HAVING
  ↓
Which groups do I keep?

ORDER BY
  ↓
How should I sort the result?
```

> 💡 Learn SQL before relying heavily on an ORM. Understanding SQL helps you understand what Prisma is doing underneath.

### 📚 Resources

[SQL Concepts and Queries — GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-concepts-and-queries/)

---

## 4.4 Database Constraints

### Important Constraints

```text
PRIMARY KEY
FOREIGN KEY
UNIQUE
NOT NULL
CHECK
DEFAULT
```

Constraints allow the **database itself** to enforce rules about the data.

Example:

```sql
email TEXT UNIQUE NOT NULL
```

This prevents:

* `NULL` emails
* Duplicate emails

---

## 4.5 Indexes

### 💡 What is an Index?

An **index** is a data structure that allows the database to find rows more efficiently for certain queries.

Conceptually:

```text
Without index
Query
  ↓
Search many rows

With useful index
Query
  ↓
Index
  ↓
Matching rows
```

Indexes can improve reads, but they also:

* Consume storage
* Add overhead to writes
* Need to be chosen carefully

Later topics:

```text
Composite indexes
Index selectivity
EXPLAIN
Query optimization
```

---

## 4.6 Transactions

A **transaction** groups multiple database operations into a single logical unit.

```text
BEGIN
  ↓
Operation 1
  ↓
Operation 2
  ↓
Operation 3
  ↓
COMMIT
```

If something goes wrong:

```text
ROLLBACK
```

### ACID

```text
A → Atomicity
C → Consistency
I → Isolation
D → Durability
```

---

[← N+1 Problem](./03-n-plus-one.md) | [Back to Databases →](./README.md)
