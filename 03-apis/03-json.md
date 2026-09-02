# 3. JSON

### 📚 Resources

* [What is JSON? (JavaScript Object Notation)](https://www.youtube.com/watch?v=KMLOWkGAxVc)
* [What is JSON? (JavaScript Object Notation) 2](https://www.youtube.com/watch?v=cj3h3Fb10QY)
* [What is JSON API](https://www.youtube.com/watch?v=N-4prIh7t38&t=1s)

### 💡 My Explanation

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

[← REST API](./02-rest-api.md) | [Next: REST + JSON Workflow →](./04-rest-json-workflow.md)
