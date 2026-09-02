# 5. Other API Styles & Protocols

REST is not the only way to build APIs. Different API technologies solve different communication and data-access problems.

---

## 5.1 SOAP

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

## 5.2 gRPC

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

## 5.3 GraphQL

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

## 6. OpenAPI Specification

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

## 7. API Technology Comparison

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

### 📌 API Interview Questions

https://www.youtube.com/watch?v=faMdrSCVDzc&t=29s

---

[← REST + JSON Workflow](./04-rest-json-workflow.md) | [Back to APIs →](./README.md)
