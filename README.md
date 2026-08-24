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

This repository is my personal journey through the **Backend Developer Roadmap**. Each section covers a key concept with curated resources and my own explanation to reinforce my learning.

> 🗺️ Full interactive roadmap available at [roadmap.sh/backend](https://roadmap.sh/backend)

---

## 📚 Table of Contents

- [1. What is HTTP?](#1-what-is-http)
- [2. What is a Domain Name?](#2-what-is-a-domain-name)
- [3. What is Web Hosting?](#3-what-is-web-hosting)
- [4. What is DNS and How it Works?](#4-what-is-dns-and-how-it-works)

---

## 🌐 Backend Fundamentals

### 1. What is HTTP?

#### 📺 Resources

> This one is a bit long but very helpful!

| Resource | Link |
|----------|------|
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=iYM2zFP3Zn0&t=717s) |
| ⚡ Short Clip | [Watch on YouTube Shorts](https://www.youtube.com/watch?v=jIvqyuZ0fBA) |

#### 💡 My Explanation

**HTTP** stands for **HyperText Transfer Protocol** — a set of rules for communication between a web server and a client, forming the **HTTP request/response cycle**.

- 🔁 **Stateless**: Every request is completely independent of the others.
- 🗃️ To work around statelessness, we use: **Local Storage**, **Cookies**, and **Sessions**.

---

### 2. What is a Domain Name?

#### 📺 Resources

> This video covers everything you need to know about Domain Names.

| Resource | Link |
|----------|------|
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=qO5qcQgiNX4) |

#### 💡 My Explanation

In simple terms, a **domain name** is the address of your website — what users type into the browser to access it.

- 🤖 Your computer understands: `172.217.160.142` *(IP Address)*
- 🧑 Humans understand: `google.com` *(Domain Name)*

> [!NOTE]
> You need to understand **DNS** to fully understand how Domain Names work. See section 4 below.

---

### 3. What is Web Hosting?

#### 📺 Resources

| Resource | Link |
|----------|------|
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=AXVZYzw8geg) |

#### 💡 My Explanation

Even with a domain name, no one can access your website unless it is **hosted**.

**Web Hosting** is a service that stores your website files on a server and makes them accessible on the internet.

| Hosting Type | Description | Best For |
|--------------|-------------|----------|
| 🤝 Shared Hosting | You share a server with others | Beginners / Cheapest option |
| 🖥️ VPS Hosting | Your own virtual private server | Small businesses |
| 💪 Dedicated Hosting | Your own physical server | High-traffic websites |
| ☁️ Cloud Hosting | Uses a cloud computing platform | Large businesses / Scalability |

---

### 4. What is DNS and How it Works?

#### 📺 Resources

> A very good video to understand DNS and how it works!

| Resource | Link |
|----------|------|
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=Wj0od2ag5sk) |

#### 💡 My Explanation

**DNS** (Domain Name System) is like a **phonebook for the internet** — it translates human-readable domain names into IP addresses that computers can understand.

```
User types:  google.com
     ↓
DNS Lookup:  google.com → 142.250.80.46
     ↓
Browser connects to the IP address
```

---

<p align="center">
  <i>📌 This roadmap is a living document — more topics will be added as I progress!</i>
</p>



## 🌐 Databases

### 1. Relational Databases vs non-Relational Databases


#### 📺 Resources

| Resource | Link |
|----------|------|
| 🎬 Full Video | [Watch on YouTube](https://www.youtube.com/watch?v=E9AgJnsEvG4) |

#### 💡 My Explanation

Relational databases (or SQL databases) store data in tables with predefined rows and columns, much like a spreadsheet.
Non-relational databases (or NoSQL databases) are more flexible and can store data in various formats like documents, key-value pairs, or graphs.

| Feature | Relational (SQL) | Non-Relational (NoSQL) |
|---------|------------------|------------------------|
| Structure | Rigid tables with rows/columns | Flexible (documents, key-value, etc.) |
| Schema | Predefined and fixed | Dynamic and flexible |
| Scalability | Vertical (increase server power) | Horizontal (add more servers) |
| Best for | Structured data, complex queries | Unstructured data, fast scaling |
| Examples | MySQL, PostgreSQL | MongoDB, Redis |



### 2. What is a Migration?

#### 📺 Resources

| Resource | Link |
|----------|------|
| 🎬 Full Video | [Watch on YouTube](https://youtu.be/mMsZPZKNc4g?si=Lqm_VO7zPHAZ5NBo) |

#### 💡 My Explanation
in simple terms, a migration is a version control system for your database. it allows you to track changes to your database schema over time, and to roll back to a previous version if needed. it's like git for your database.

#### Types of Migrations

**Schema Migrations** : **The Blueprint Alterations**
A database schema is like the blueprint of a house, showing the structure and layout of the database. Schema migrations are changes made to this "blueprint" to meet new needs. For instance, removing a table column is like taking down a wall to open up space, and adding a new table is like building an extra floor. These changes help the database stay efficient and fit the changing needs of a business, similar to how renovating a house makes it more comfortable and functional over time.
Schema migrations can include:
Adding, altering, or dropping tables: Just as you'd add or remove rooms in a house.
Changing data types of columns: Think of this as repurposing a room – from an office to a bedroom, perhaps.
Introducing or changing indices: This is like optimizing the flow and accessibility within your house, ensuring you can fetch what you need faster.

**Data Migrations** : **The Furniture Relocation**
If schema migration is about altering the house blueprint, data migration is about moving the furniture within and ensuring it fits well. It deals directly with the data in the database — the actual information, not just its structure.
Picture relocating from one house to another. You'd be moving sofas, beds, chairs, and every cherished possession. Data migration works similarly. You might be:
Transferring data from one database system to another: Like moving belongings from an old house to a brand new one.
Upgrading a database version: Imagine shifting from an old-styled interior to a modern, contemporary design.
Changing the way data is stored and accessed: This can be likened to reorganizing your house, maybe changing which room is the living room and which is the dining room.
But remember, just as with moving houses, it's essential to ensure no 'furniture' (data) gets lost or damaged during the process.


### 2. What is the N+1 problem?

#### 📺 Resources

https://www.youtube.com/watch?v=XjYD8SQnfUw

https://medium.com/databases-in-simple-words/the-n-1-database-query-problem-a-simple-explanation-and-solutions-ef11751aef8a

#### 💡 My Explanation

The N+1 query problem is a common issue in database interactions where an application executes one query to fetch a list of items, and then executes an additional query for each item in that list. This results in N+1 queries, where N is the number of items fetched.

### 3. PostgreSQL

#### 3.1 What is SQL?

SQL is structured query language used to interact with relational databases. It is a declarative language, which means that it is used to describe the data that needs to be retrieved or manipulated.

#### 3.2 Relational concepts

##### 3.2.1 Tables
Tables are the basic unit of storage in a relational database. They are organized in a tabular format with rows and columns.

##### 3.2.2 Primary keys
Primary keys are used to uniquely identify each row in a table.

##### 3.2.3 Foreign keys
Foreign keys are used to establish relationships between tables.

all you need is here : https://www.geeksforgeeks.org/sql/sql-concepts-and-queries/

##### 3.2.4 Relationships
Relationships are used to establish relationships between tables.
**one to one relationship** : is when one record in one table can be related to only one record in another table.

**one to many relationship** : is when one record in one table can be related to many records in another table.

**many to many relationship** : is when one record in one table can be related to many records in another table, and one record in another table can be related to many records in the first table.

#### Resources

https://www.youtube.com/watch?v=WOX9g1s43-g

https://medium.com/@patrikstrausz17/part3-postgresql-relationships-creating-and-managing-database-relationships-5e1eaea769d8



