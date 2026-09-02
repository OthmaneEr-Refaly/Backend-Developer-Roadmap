# 4. REST + JSON Workflow

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

[← JSON](./03-json.md) | [Next: Other API Styles →](./05-other-api-styles.md)
