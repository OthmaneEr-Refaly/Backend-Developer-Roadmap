# 2. Database Migrations

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

[← Relational vs NoSQL](./01-relational-vs-nosql.md) | [Next: N+1 Problem →](./03-n-plus-one.md)
