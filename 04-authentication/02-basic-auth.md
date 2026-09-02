# 2. Basic Authentication

### 📖 Definition

**Basic Authentication (Basic Auth)** is an HTTP authentication scheme where the client sends a **username and password** with each request that requires authentication.

The credentials are combined as:

```text
username:password
```

and then **Base64 encoded** and sent through the `Authorization` header:

```http
Authorization: Basic <base64-credentials>
```

> ⚠️ **Base64 is encoding, not encryption.** Basic Auth should therefore be used with **HTTPS/TLS** so that credentials cannot be easily intercepted.

### ✅ Pros

* **Simple** — easy to understand and implement.
* **Widely supported** — built directly into HTTP clients, browsers, and servers.
* **Stateless** — the server does not need to maintain a login session.
* **Easy to test** — convenient for APIs, internal tools, and development environments.
* **No token management** — there are no JWTs, refresh tokens, or sessions to manage.

### ❌ Cons

* **Credentials are sent with every request**.
* **Base64 is not encryption** — credentials can be decoded.
* **Requires HTTPS** for secure use.
* **Poor credential lifecycle management** — changing or revoking credentials can be inconvenient.
* **Not ideal for modern user-facing applications**.
* Can be particularly vulnerable to **credential exposure and CSRF-related issues** depending on how it is used.

### 🧠 Mental Model

> **Basic Auth = "Here is my username and password again."**

Unlike session or token-based authentication, the client generally sends the credentials themselves with each authenticated request.

### 🖼️ Diagram

![Basic Authentication Flow](../assets/Basic%20Auth.png)

### 📚 Resources

* [Basic Authentication](https://www.youtube.com/watch?v=rhi1eIjSbvk)
* [MDN — HTTP Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Authentication)
* [MDN — Authorization Header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Authorization)
* [RFC 7617 — The 'Basic' HTTP Authentication Scheme](https://www.rfc-editor.org/rfc/rfc7617.html)

---

[← Auth vs Authz](./01-auth-vs-authz.md) | [Next: Session Auth →](./03-session-auth.md)
