# 1. Relational vs Non-Relational Databases

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

[← Back to Databases](./README.md) | [Next: Migrations →](./02-migrations.md)
