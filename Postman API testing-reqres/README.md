# 🧪 ReqRes API Testing with Postman

A comprehensive API testing collection for [ReqRes](https://reqres.in/) — a hosted REST API designed for testing and prototyping.

---

## 📌 Project Overview

This project contains a full suite of API tests built in **Postman**, covering all major endpoints provided by the ReqRes public API. It demonstrates real-world API testing practices including CRUD operations, authentication, error handling, and response validation.

---

## 🔗 Base URL

```
https://reqres.in/api
```

---

## 📋 Endpoints Tested

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/users?page=2` | List of users |
| `GET` | `/users/2` | List single user |
| `GET` | `/users/23` | User not found (404) |
| `GET` | `/unknown` | List all resources |
| `GET` | `/unknown/2` | List a resource |
| `POST` | `/users` | Create user |
| `PUT` | `/users/2` | Update a user |
| `PATCH` | `/users/2` | Update a user (patch) |
| `POST` | `/register` | Register (successful) |
| `POST` | `/register` | Register (unsuccessful) |
| `DELETE` | `/users/2` | Delete a user |
| `GET` | `/login` | Login successful |
| `GET` | `/login` | Login unsuccessful |
| `GET` | `/users?delay=3` | Delayed response |

---

## ✅ Test Cases & Assertions

Each request includes test scripts to validate:

- **Status codes** (200, 201, 204, 400, 404)
- **Response body structure** (correct fields present)
- **Response time** (< 2000ms)
- **Data type validation** (strings, integers, emails)
- **Content-Type headers** (`application/json`)

### Example Test Script (Create User)

```javascript
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Response has name and job", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("name");
    pm.expect(jsonData).to.have.property("job");
    pm.expect(jsonData).to.have.property("id");
    pm.expect(jsonData).to.have.property("createdAt");
});

pm.test("Response time is less than 2000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});
```

---

## 🚀 How to Run

### Prerequisites
- [Postman](https://www.postman.com/downloads/) installed
- Internet connection (ReqRes is a live hosted API)

### Steps

1. **Clone this repository**
   ```bash
   git clone https://github.com/your-username/reqres-api-testing.git
   cd reqres-api-testing
   ```

2. **Import collection into Postman**
   - Open Postman
   - Click **Import**
   - Select `ReqRes.postman_collection.json`

3. **Run all tests**
   - Open the collection in Postman
   - Click **Run collection**
   - Review the test results


---


## 📊 Test Results

| Test | Status |
|------|--------|
| GET List of Users - Status 200 | ✅ Pass |
| GET Single User - Status 200 | ✅ Pass |
| GET User Not Found - Status 404 | ✅ Pass |
| POST Create User - Status 201 | ✅ Pass |
| PUT Update User - Status 200 | ✅ Pass |
| PATCH Update User - Status 200 | ✅ Pass |
| DELETE User - Status 204 | ✅ Pass |
| POST Register Success - Status 200 | ✅ Pass |
| POST Register Fail - Status 400 | ✅ Pass |
| GET Delayed Response - Status 200 | ✅ Pass |

---

## 🛠️ Tools & Technologies

- **Postman** — API testing and collection management
- **ReqRes API** — Public REST API for testing

---

