# 1. Authentication vs Authorization

## Authentication

**Authentication** answers: **Who are you?**

It is the process of verifying the identity of a user or system.

## Authorization

**Authorization** answers: **What are you allowed to do?**

It is the process of determining what an authenticated user is permitted to access or perform.

## Authentication vs Authorization

```text
Authentication
       ↓
"Prove who you are"
       ↓
Login / Credentials / Token

Authorization
       ↓
"What can you do?"
       ↓
Permissions / Roles / Access Control
```

> ⚠️ Authorization typically happens **after** authentication.
> You first verify who the user is, then check what they are allowed to do.

### Different Types of Authentication

- [Basic Authentication](./02-basic-auth.md)
- [Session-Based Authentication](./03-session-auth.md)
- [JSON Web Token (JWT)](./04-jwt.md)

---

[← Back to Authentication](./README.md) | [Next: Basic Auth →](./02-basic-auth.md)
