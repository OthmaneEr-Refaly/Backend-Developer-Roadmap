# 2. What is a REST API?

### 📚 Resources

* [What is REST API?](https://www.youtube.com/watch?v=lsMQRaeKNDk&t=170s)
* [In more depth](https://www.youtube.com/watch?v=1Wl-rtew1_E)

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

[← What is an API?](./01-what-is-an-api.md) | [Next: JSON →](./03-json.md)
