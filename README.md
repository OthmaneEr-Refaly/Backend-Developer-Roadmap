# 🚀 Backend Developer Roadmap

<p align="center">
  <a href="https://roadmap.sh/backend">
    <img src="./assets/roadmmap.png" alt="Backend Developer Roadmap" width="900"/>
  </a>
</p>

<p align="center">
  <a href="https://roadmap.sh/backend">
    <img src="https://img.shields.io/badge/roadmap.sh-Backend%20Roadmap-blue?style=for-the-badge" alt="Roadmap Badge"/>
  </a>
  <img src="https://img.shields.io/badge/Status-In%20Progress-yellow?style=for-the-badge" alt="Status Badge"/>
  <img src="https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=for-the-badge" alt="Made with love"/>
</p>

---

## 📖 About

This repository is my personal journey through the **Backend Developer Roadmap**.

Each section contains:

* 📚 Resources I used to learn the topic
* 💡 My own explanation and mental model
* 📝 Important concepts I want to remember
* 🔗 Connections between different backend concepts

The goal is not to memorize everything, but to build a strong understanding of **how backend systems work and why they are designed the way they are**.

> 🗺️ Full interactive roadmap: [roadmap.sh/backend](https://roadmap.sh/backend)

---

## 📚 Table of Contents

### 🌐 Backend Fundamentals

* [1. What is HTTP?](#1-what-is-http)
* [2. What is a Domain Name?](#2-what-is-a-domain-name)
* [3. What is Web Hosting?](#3-what-is-web-hosting)
* [4. What is DNS and How it Works?](#4-what-is-dns-and-how-it-works)

### 🗄️ Databases

* [1. Relational vs Non-Relational Databases](#1-relational-vs-non-relational-databases)
* [2. Database Migrations](#2-database-migrations)
* [3. N+1 Query Problem](#3-n1-query-problem)
* [4. PostgreSQL](#4-postgresql)

### 🔌 APIs

* [1. What is an API?](#1-what-is-an-api)
* [2. What is a REST API?](#2-what-is-a-rest-api)
* [3. JSON](#3-json)
* [4. REST + JSON Workflow](#4-rest--json-workflow)

---

# 🌐 Backend Fundamentals

## 1. What is HTTP?

### 📺 Resources

> This one is a bit long but very helpful!

| Resource      | Link                                                                   |
| ------------- | ---------------------------------------------------------------------- |
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=iYM2zFP3Zn0&t=717s) |
| ⚡ Short Clip  | [Watch on YouTube Shorts](https://www.youtube.com/watch?v=jIvqyuZ0fBA) |

### 💡 My Explanation

**HTTP** stands for **HyperText Transfer Protocol**.

It is a set of rules that allows clients and servers to communicate using a **request/response cycle**.

```text
Client
  │
  │ HTTP Request
  ▼
Server
  │
  │ HTTP Response
  ▼
Client
```

HTTP is **stateless**, meaning each request is independent. The server does not automatically remember previous requests.

To maintain state, applications can use mechanisms such as:

* Cookies
* Sessions
* Local Storage
* Tokens

### 🔑 Important Concepts

* HTTP Request
* HTTP Response
* HTTP Methods
* HTTP Headers
* HTTP Status Codes
* Request Body
* Response Body
* Statelessness

---

## 2. What is a Domain Name?

### 📺 Resources

| Resource      | Link                                                            |
| ------------- | --------------------------------------------------------------- |
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=qO5qcQgiNX4) |

### 💡 My Explanation

A **domain name** is a human-readable address used to access a website or service.

For example:

```text
google.com
```

Computers ultimately communicate using IP addresses:

```text
142.250.80.46
```

DNS is responsible for resolving the domain name to an IP address.

> 💡 See [DNS](#4-what-is-dns-and-how-it-works) to understand how this works.

---

## 3. What is Web Hosting?

### 📺 Resources

| Resource      | Link                                                            |
| ------------- | --------------------------------------------------------------- |
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=AXVZYzw8geg) |

### 💡 My Explanation

**Web hosting** means making an application or website available on a server that can be accessed over a network such as the internet.

Common hosting approaches include:

| Type              | Description                                     |
| ----------------- | ----------------------------------------------- |
| 🤝 Shared Hosting | Multiple websites share server resources        |
| 🖥️ VPS           | A virtual private server                        |
| 💪 Dedicated      | An entire physical server                       |
| ☁️ Cloud          | Infrastructure provided through cloud platforms |

---

## 4. What is DNS and How it Works?

### 📺 Resources

> A very good video to understand DNS and how it works!

| Resource      | Link                                                            |
| ------------- | --------------------------------------------------------------- |
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=Wj0od2ag5sk) |

### 💡 My Explanation

**DNS (Domain Name System)** translates domain names into IP addresses.

Think of it as a directory that helps computers find the server associated with a domain.

```text
User enters:

google.com
     ↓
DNS Lookup
     ↓
IP Address
     ↓
Browser connects to server
```

---

# 🗄️ Databases

## 1. Relational vs Non-Relational Databases

### 📺 Resources

| Resource      | Link                                                            |
| ------------- | --------------------------------------------------------------- |
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=E9AgJnsEvG4) |

### 💡 My Explanation

### Relational Databases

Relational databases organize data into **tables consisting of rows and columns** and use relationships between tables to represent connected data.

They typically use SQL for querying and manipulating data.

Example:

```text
USERS
┌─────────┬──────────┐
│ user_id │ name     │
├─────────┼──────────┤
│ 1       │ Othmane  │
│ 2       │ Ahmed    │
└─────────┴──────────┘
```

Examples:

* PostgreSQL
* MySQL
* MariaDB
* SQL Server
* Oracle

### Non-Relational Databases

Non-relational databases use other data models depending on the problem they solve.

Examples include:

```text
Document       → MongoDB
Key-Value      → Redis
Graph          → Neo4j
Wide-Column    → Cassandra
```

The choice between relational and non-relational databases depends on factors such as:

* Data structure
* Relationships
* Query patterns
* Consistency requirements
* Scalability requirements
* Application workload

> ⚠️ Avoid thinking of SQL databases as "vertical scaling" and NoSQL databases as "horizontal scaling." Both types can use different scaling strategies.

---

## 2. Database Migrations

### 📺 Resources

| Resource      | Link                                                                 |
| ------------- | -------------------------------------------------------------------- |
| 🎬 Full Video | [Watch on YouTube](https://youtu.be/mMsZPZKNc4g?si=Lqm_VO7zPHAZ5NBo) |

### 💡 My Explanation

A **database migration** is a versioned, controlled change to a database.

It allows developers to track how the database schema evolves over time.

Think:

```text
Version 1
   ↓
Migration 1
   ↓
Version 2
   ↓
Migration 2
   ↓
Version 3
```

Migration files can be stored in Git alongside the application code.

### Schema Migration

A **schema migration** changes the structure of the database.

Examples:

* Add a table
* Remove a table
* Add a column
* Remove a column
* Change a column type
* Add/remove an index
* Add/change constraints

### Data Migration

A **data migration** changes or transforms the actual data.

For example:

```text
Before:

name
----------------
Othmane Er Refaly
Ahmed Alaoui
```

After:

```text
first_name | last_name
-----------|-----------
Othmane    | Er Refaly
Ahmed      | Alaoui
```

### ⚠️ Important Migration Problems

Migrations can become complicated because:

* Existing data must remain valid
* Old application versions may still be running
* Large tables can make changes expensive
* Some changes can cause downtime or locking
* Data transformations may be difficult to reverse
* Multiple application versions may need to work with the database simultaneously

### Common Strategies

```text
Backward-compatible migrations
        ↓
Expand → Migrate → Contract
        ↓
Zero-downtime / online migrations
```

> ⚠️ A migration is similar to version control for database changes, but it is **not exactly "Git for the database."** Git tracks code/history; migration systems track and apply database changes.

---

## 3. N+1 Query Problem

### 📺 Resources

* [Watch on YouTube](https://www.youtube.com/watch?v=XjYD8SQnfUw)
* [Read on Medium](https://medium.com/databases-in-simple-words/the-n-1-database-query-problem-a-simple-explanation-and-solutions-ef11751aef8a)

### 💡 My Explanation

The **N+1 query problem** happens when an application performs:

```text
1 query to fetch N items
        +
1 additional query for each item
        =
N + 1 queries
```

Example:

```text
Get 100 users
       ↓
1 query

Then get posts for each user
       ↓
100 more queries

Total = 101 queries
```

This can cause unnecessary database load and poor performance.

Common solutions include:

* JOINs
* Eager loading
* Batching
* Data loaders
* ORM relation loading strategies

> 💡 I only need a surface-level understanding of this concept for now. Deeper optimization comes later.

---

# PostgreSQL

## 4. PostgreSQL

### 💡 What is PostgreSQL?

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

# 🔌 APIs

## 1. What is an API?

### 📚 Resources

[What is an API? (Application Programming Interface)](https://www.youtube.com/watch?v=bxuYDT-BWaI)

### 💡 My Explanation

**API** stands for **Application Programming Interface**.

An API defines a way for different software components to communicate with each other.

For web backend development, an API commonly allows a client to communicate with a server over HTTP.

```text
Frontend / Client
        │
        │ HTTP Request
        ▼
      API
        │
        ▼
     Backend
        │
        ▼
    Database
```

Example:

```text
GET /books
```

The client is asking the server for books.

---

## 2. What is a REST API?

### 📚 Resources

[What is REST API?](https://www.youtube.com/watch?v=lsMQRaeKNDk&t=170s)

[In more depth](https://www.youtube.com/watch?v=1Wl-rtew1_E)

### 💡 My Explanation

**REST** stands for **Representational State Transfer**.

REST is an **architectural style** for designing networked applications and APIs.

REST encourages APIs to be designed around **resources**.

For example:

```text
/books
/users
/orders
```

HTTP methods describe operations on those resources:

```text
GET    /books
GET    /books/123
POST   /books
PUT    /books/123
PATCH  /books/123
DELETE /books/123
```

### REST Mental Model

```text
Resource
   +
HTTP methods
   +
HTTP status codes
   +
Stateless communication
   +
Resource representations
```

> ⚠️ REST does not require JSON.

An API can use JSON, XML, HTML, or another representation format.

---

## 3. JSON

###  Resources

[What is JSON? (JavaScript Object Notation)](https://www.youtube.com/watch?v=KMLOWkGAxVc)

[What is JSON? (JavaScript Object Notation)2](https://www.youtube.com/watch?v=cj3h3Fb10QY)

[What is JSON API](https://www.youtube.com/watch?v=N-4prIh7t38&t=1s)

###  My Explanation

**JSON** stands for **JavaScript Object Notation**.

JSON is a **text-based data interchange format** used to represent and exchange structured data.

It is:

* Human-readable
* Machine-readable
* Language-independent
* Commonly used by web APIs
* Not limited to JavaScript

Example:

```json
{
  "id": 123,
  "title": "Clean Code",
  "price": 30,
  "available": true
}
```

### JSON Data Types

JSON supports:

```text
String
Number
Boolean
Null
Object
Array
```

Example:

```json
{
  "name": "Othmane",
  "age": 26,
  "active": true,
  "nickname": null,
  "skills": ["TypeScript", "SQL"],
  "address": {
    "city": "Rabat"
  }
}
```

> 💡 JSON is a way to **represent data**, not a database and not an API itself.

---

## 4. REST + JSON Workflow

REST and JSON describe **different things**.

```text
REST
↓
How the API is designed

JSON
↓
How data is represented
```

Therefore:

```text
REST API + JSON
```

is an extremely common combination.

### Example Request

```http
GET /books/123
Accept: application/json
```

`Accept` means:

> "I would like the response in JSON."

### Example Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "id": 123,
  "title": "Clean Code",
  "price": 30
}
```

`Content-Type` tells the client:

> "The data I'm sending is JSON."

---

## 4.1 Accept vs Content-Type

### Accept

```http
Accept: application/json
```

Means:

> **What format do I want to receive?**

### Content-Type

```http
Content-Type: application/json
```

Means:

> **What format is the data I'm sending?**

They can appear together:

```http
POST /books
Content-Type: application/json
Accept: application/json
```

Meaning:

> "I'm sending JSON and I would like JSON back."

---

## 4.2 Complete REST + JSON Workflow

```text
CLIENT
  │
  │ GET /books/123
  │ Accept: application/json
  ▼
SERVER
  │
  ├── Route
  ├── Controller
  ├── Service
  ├── Database / Prisma
  │
  ▼
SERVER DATA
  │
  │ Convert/serialize to JSON
  ▼
HTTP RESPONSE
  │
  │ 200 OK
  │ Content-Type: application/json
  ▼
CLIENT
  │
  ▼
JSON → Application Data → UI
```

For a POST:

```text
CLIENT
  │
  │ POST /books
  │ Content-Type: application/json
  ▼
SERVER
  │
  ├── Parse JSON
  ├── Validate data
  ├── Business logic
  ├── Database
  │
  ▼
JSON RESPONSE
```

---

## 🧠 Important Mental Models

### Backend Request Flow

```text
Client
  ↓
HTTP
  ↓
API
  ↓
Controller
  ↓
Service
  ↓
Database / Prisma
  ↓
PostgreSQL
```

### API Communication

```text
HTTP
 ↓
Communication protocol

REST
 ↓
API architectural style

JSON
 ↓
Data representation format
```

### Database

```text
Application
     ↓
Prisma
     ↓
SQL
     ↓
PostgreSQL
     ↓
Tables / Rows / Data
```

---

## 5. Other API Styles & Protocols

REST is not the only way to build APIs. Different API technologies solve different communication and data-access problems.

---

### 5.1 SOAP

### 💡 What is SOAP?

**SOAP (Simple Object Access Protocol)** is a protocol for exchanging structured information between applications.

It commonly uses **XML** to format messages and usually operates over HTTP, although SOAP is not limited to HTTP.

Example:

```xml
<soap:Envelope>
    <soap:Body>
        <GetUser>
            <UserId>123</UserId>
        </GetUser>
    </soap:Body>
</soap:Envelope>
```

### 🧠 Main Characteristics

* Uses XML
* Strictly structured messages
* Defines a formal messaging protocol
* Supports features such as security and transactions
* Commonly found in enterprise and legacy systems

### REST vs SOAP

|               | REST                           | SOAP                             |
| ------------- | ------------------------------ | -------------------------------- |
| Type          | Architectural style            | Protocol                         |
| Data format   | Usually JSON                   | XML                              |
| Structure     | Flexible                       | Strict                           |
| Communication | Commonly HTTP                  | Can use HTTP and other protocols |
| Typical usage | Web APIs / modern applications | Enterprise / legacy systems      |

> 💡 SOAP is more than "REST but with XML". SOAP defines a formal messaging protocol, while REST is an architectural style.

### 📚 Resources

https://www.youtube.com/watch?v=pBASqUbZgkY&t=95s

---

### 5.2 gRPC

### 💡 What is gRPC?

**gRPC** is a high-performance RPC (Remote Procedure Call) framework originally developed by Google.

Instead of thinking primarily in terms of resources like REST:

```text
GET /users/123
```

gRPC focuses on calling **remote methods/functions**:

```text
GetUser(123)
```

gRPC commonly uses:

* **HTTP/2** for transport
* **Protocol Buffers (Protobuf)** for defining services and messages
* Generated client/server code

Example service definition:

```protobuf
service UserService {
    rpc GetUser(GetUserRequest) returns (User);
}
```

### 🧠 Main Characteristics

* High performance
* Uses HTTP/2
* Uses Protocol Buffers by default
* Strongly typed
* Supports code generation
* Well suited for communication between backend services

### REST vs gRPC

|               | REST                       | gRPC                              |
| ------------- | -------------------------- | --------------------------------- |
| Style         | Resource-based             | RPC / method-based                |
| Common format | JSON                       | Protobuf                          |
| Transport     | Usually HTTP/1.1 or HTTP/2 | HTTP/2                            |
| Typing        | Usually looser             | Strongly typed                    |
| Performance   | Good                       | Often faster                      |
| Common usage  | Public APIs / web clients  | Internal services / microservices |

> 💡 gRPC does not replace REST everywhere. It is particularly useful when multiple backend services need efficient, strongly typed communication.

### 📚 Resources

https://www.youtube.com/watch?v=pBASqUbZgkY&t=95s

---

### 5.3 GraphQL

### 💡 What is GraphQL?

**GraphQL** is a query language and runtime for APIs.

Instead of the server deciding exactly which fields a REST endpoint returns, the client can specify **which data it wants**.

For example:

```graphql
query {
    user(id: 123) {
        name
        email
    }
}
```

The server returns the requested fields:

```json
{
    "data": {
        "user": {
            "name": "Othmane",
            "email": "othmane@example.com"
        }
    }
}
```

### 🧠 Main Characteristics

* Client specifies the data it needs
* Strongly typed schema
* Usually uses a single endpoint
* Can retrieve related data in one query
* Helps reduce over-fetching and under-fetching

### REST vs GraphQL

With REST, you might have:

```text
GET /users/123
GET /users/123/orders
GET /users/123/books
```

With GraphQL, the client can request the related data in one query:

```graphql
query {
    user(id: 123) {
        name
        orders {
            id
        }
        books {
            title
        }
    }
}
```

### ⚠️ Important

GraphQL is **not simply "REST but better."**

It solves different problems and introduces its own complexity, such as:

* Query complexity
* Caching
* Authorization
* N+1 problems
* Schema management

### 📚 Resources

https://www.youtube.com/watch?v=pBASqUbZgkY&t=95s

---

# 6. OpenAPI Specification

### 💡 What is OpenAPI?

**OpenAPI Specification (OAS)** is a standard for describing HTTP APIs in a machine-readable format.

It can describe things such as:

* Available endpoints
* HTTP methods
* Parameters
* Request bodies
* Response bodies
* Authentication
* Status codes
* Data schemas

Example:

```yaml
openapi: 3.0.0

paths:
  /users/{id}:
    get:
      summary: Get a user
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: integer
      responses:
        "200":
          description: Successful response
```

### 🧠 Why is OpenAPI useful?

Instead of having API documentation written separately from the code, we can describe the API using a standardized specification.

Tools can then use the specification to:

```text
OpenAPI Specification
        │
        ├── API Documentation
        │
        ├── Swagger UI
        │
        ├── Client Generation
        │
        ├── Server Generation
        │
        └── Testing / Validation
```

### OpenAPI vs Swagger

These terms are often confused.

**OpenAPI** = the specification/standard.

**Swagger** = a collection of tools built around the OpenAPI specification.

For example:

```text
OpenAPI Specification
        ↓
Swagger UI
        ↓
Interactive API documentation
```

> 💡 Think of OpenAPI as the **blueprint/description of an API**, not the API itself.

### 📚 Resources

https://www.youtube.com/watch?v=pRS9LRBgjYg

---

# 7. API Technology Comparison

A quick mental map:

| Technology | Main Idea                     | Common Data Format | Common Use                       |
| ---------- | ----------------------------- | ------------------ | -------------------------------- |
| REST       | Resource-based API            | JSON               | Web / public APIs                |
| SOAP       | Formal messaging protocol     | XML                | Enterprise / legacy systems      |
| gRPC       | Remote procedure calls        | Protobuf           | Service-to-service communication |
| GraphQL    | Client-defined queries        | JSON               | Flexible data fetching           |
| OpenAPI    | API description/specification | YAML / JSON        | Documentation / tooling          |

### 🧠 Important Distinction

These technologies are not all directly competing with each other.

```text
REST
SOAP
gRPC
GraphQL
    ↓
Ways of building / communicating with APIs


OpenAPI
    ↓
A way of describing an API
```

And JSON is a **data representation format**, not an API style:

```text
REST ────────┐
GraphQL ─────┤
             ├── can use JSON
Other APIs ──┘

JSON
↓
Data representation
```

---


# 📌 API Interview Questions
https://www.youtube.com/watch?v=faMdrSCVDzc&t=29s
# 📌 API Interview Questions



# 📌 API Topics — Current Progress

### ✅ Learned

* What is an API?
* HTTP APIs
* REST
* REST + JSON
* JSON
* Accept vs Content-Type
* SOAP
* gRPC
* GraphQL
* OpenAPI Specification

### 🔜 To Learn Later

* HTTP methods in depth
* HTTP status codes
* HTTP headers
* Authentication
* Authorization
* Cookies
* Sessions
* JWT
* API validation
* API error handling
* API versioning
* Pagination
* Filtering
* Rate limiting
* CORS
* API testing
* Swagger / OpenAPI with NestJS
* API security


---

<p align="center">
  <i>📌 This roadmap is a living document — more topics will be added as I progress!</i>
</p>
