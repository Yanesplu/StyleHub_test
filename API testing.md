# API Testing

API testing for the **StyleHub e-commerce application** was performed using **Postman** based on the available API documentation.

API documentation is available here:

https://qatestingapp.netlify.app/api-docs

---

# API Testing Scope

The following aspects were validated during API testing:

- HTTP status codes
- Response body structure
- Required fields validation
- Authorization checks
- Error handling
- Negative scenarios
- Data persistence in database

---

# API Endpoints Tested

| Endpoint | Method | Description |
|--------|--------|--------|
| `/api/register` | POST | Register new user |
| `/api/login` | POST | User authentication |
| `/api/products` | GET | Retrieve list of products |
| `/api/products/:id` | GET | Retrieve product details |
| `/api/cart` | POST | Add product to cart |
| `/api/cart` | GET | Retrieve cart items |
| `/api/orders` | POST | Create order |
| `/api/orders` | GET | Retrieve user orders |
| `/api/reviews` | POST | Add product review |

---

# Example API Test

## Login API

### Request

```
POST /api/login
```

### Request Body

```json
{
  "email": "test@test.com",
  "password": "123456"
}
```

### Expected Response

```json
{
  "success": true,
  "user": {
    "id": 1,
    "email": "test@test.com"
  }
}
```

### Validation

- Status code = **200 OK**
- Response contains **user object**
- Authentication token returned
- User session created

---

# Negative API Testing

Examples of negative scenarios tested:

| Test Case | Expected Result |
|--------|--------|
| Missing required fields | 400 Bad Request |
| Invalid credentials | 401 Unauthorized |
| Access without authorization | 401 Unauthorized |
| Non-existing endpoint | 404 Not Found |
| Server error scenario | 500 Internal Server Error |

---

# Example Error Response

```json
{
  "error": "Invalid credentials"
}
```

Expected validation:

- Proper HTTP status code returned
- Error message present in response body

---

# API Test Tools

The following tools were used during testing:

- Postman
- Browser DevTools
- Swagger API documentation

---

# API Test Artifacts

```
API-Testing/
│
├── api-testing.md
├── postman-collection.json
└── api-test-cases.md
```

---

# Example API Assertions

Typical API checks performed:

- Status code validation
- Response schema validation
- Response time validation
- Required fields validation
- Authorization validation

---

# Postman Collection

All API requests were executed using **Postman**.

The exported collection can be found in:

https://drlys21-2901611.postman.co/workspace/%D0%94%D0%B0%D1%80%D1%8C%D1%8F-%D0%9B%D1%8B%D1%81%D0%B5%D0%BD%D0%BA%D0%BE's-Workspace~f0d88598-2d9e-4f17-8837-2efa5ca39195/collection/51860899-b2ec5b41-0221-43db-9d24-edde8c6fbb44?action=share&source=copy-link&creator=51860899

API-Testing/postman-collection.json
```
