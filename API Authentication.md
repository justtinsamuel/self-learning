# API Authentication

**Main Goal:** Ensure the **right person** is accessing the **right data**.

There are three common authentication methods:

* **API Key** → Simple, unique key to access an API.
  *Use when:* small internal services or public APIs.

* **JWT (JSON Web Token)** → Self-contained token for stateless authentication.
  *Use when:* building scalable web/mobile apps.

* **OAuth** → Third-party login using providers like Google or Facebook.
  *Use when:* you want to let users log in with external accounts.

---

## 1. API Key

An **API Key** is like a **VIP access card**: a long, random string used to identify and authenticate a client.

* 🔒 Should **not** be included in the URL. Place it in **request headers** instead.
* ✅ Best use cases:

  * Public APIs (weather, maps, stock market data)
  * Internal microservices
  * Rate-limiting & analytics (tracking API usage)

---

## 2. JWT (JSON Web Token)

A **JWT** is like a **wristband at an event** — once you have it, you don’t need to show your credentials again.

**Structure:**

* **Header** → metadata (algorithm, type)
* **Payload** → claims (user data, permissions)
* **Signature** → ensures the token is not tampered with

**How it works:**

1. User logs in with credentials.
2. If valid → server generates a JWT.
3. Client stores token (e.g., `localStorage` or cookies).
4. Each request → token is sent in headers.
5. Server verifies token validity/expiration.

✅ Widely used in modern web & mobile apps.

---

## 3. OAuth

**OAuth (Open Authorization)** lets users log in with **external providers** (Google, Facebook, etc.).

* No need to create a profile first (unless the app requires setting a password later).

**How it works:**

1. User selects "Login with Google".
2. App redirects to Google for authentication.
3. User grants permission.
4. App exchanges the authorization code for an access token.
5. The token is used for authenticated requests.

✅ Common in apps that integrate with social media or external accounts.

---

## Choosing the Right Method

* Use **API Keys** for simple services or public APIs.
* Use **JWT** for scalable, stateless apps.
* Use **OAuth** when you want external login (Google, Facebook, etc.).
