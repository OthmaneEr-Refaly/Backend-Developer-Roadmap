# 3. N+1 Query Problem

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

[← Migrations](./02-migrations.md) | [Next: PostgreSQL →](./04-postgresql.md)
