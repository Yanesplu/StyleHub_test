# StyleHub QA Testing Project

Manual testing project for an **e-commerce clothing website** built with **Next.js** and **PostgreSQL**.

This project demonstrates practical QA skills including **test case design, bug reporting, API testing, and database validation**.
# https://qatestingapp.netlify.app/
---

# Project Overview

**Application type:** E-commerce clothing store  
**Architecture:** Full-stack web application  

**Tech stack:**

- Frontend: Next.js  
- Backend: Next.js API Routes  
- Database: PostgreSQL (raw SQL queries)

The goal of this project was to perform **end-to-end manual testing of a web application**, including UI, API, database, and localization checks.

---

# Testing Scope

The following features were tested:

- User registration and login
- Profile management
- Product catalog
- Product details page
- Reviews system
- Search functionality
- Shopping cart
- Mock payment flow
- Admin dashboard
- Localization (UA / ENG)

Testing included **UI validation, API testing, database checks, and security validation.**

---

# Testing Types

The following testing approaches were used:

- Functional Testing
- UI Testing
- Regression Testing
- API Testing
- Database Testing
- Localization Testing
- Negative Testing
- Basic Security Testing (SQL Injection checks)

---

# Testing Tools

Tools used during testing:

- Browser DevTools
- Postman (API testing)
- Swagger (API documentation)
- PostgreSQL console
- TestRail (test case management)

---

# Test Environment

| Component | Details |
|-----------|--------|
| OS | Windows 11 |
| Browser | Google Chrome |
| Database | PostgreSQL |
| Backend | Next.js API |
| Testing Tools | Postman, DevTools |

---

# Features Tested

## General
- Header / Footer layout
- Navigation
- Language switch
  
## Authentication
- User registration
- Login / Logout
- Email verification (mock)
- Session persistence
- Access control

## Profile
- Update name
- Change password
- View favourites
- View order history

## Product Management
- View products
- Product details page
- Add to cart
- Add to favourites
- Submit reviews

## Search
- Search by product title
- Partial match search
- Empty results scenario

## Cart
- Add products
- Remove products
- Update quantity
- Total price calculation

## Payment
- Mock payment process
- Order creation in database

## Admin Dashboard
- Create product
- Update product
- Manage users
- Change user roles
- View orders

---

# API Testing

API testing included:

- Status code validation
- Response body validation
- Authorization checks
- Negative testing scenarios

Example endpoints tested:

```
/api/login
/api/register
/api/products
/api/cart
```

---

# Database Testing

Database validation included:

- Data insertion validation
- Data update validation
- Data integrity verification
- SQL injection testing

Example SQL checks:

```sql
SELECT id, email, created_at
FROM users
WHERE email = 'test@test.com';
```

```sql
SELECT id, title, price, stock
FROM products
WHERE title ILIKE '%jacket%';
```
```sql
SELECT product_id, quantity
FROM cart_items
WHERE user_id = (
    SELECT id FROM users WHERE email = 'test@test.com'
);
```
```sql
SELECT id, user_id, total_price, created_at
FROM orders
ORDER BY created_at DESC
LIMIT 5;
```
# SQL Injection Safety Check

Example malicious input:

```
' OR 1=1 --
```

Test validation:

```sql
SELECT *
FROM users
WHERE email = 'test@test.com'
AND password = 'invalid_password';
```


---

# Test Documentation

The project includes the following QA documentation:

| Document | Description |
|--------|-------------|
| Test Plan | Overall testing strategy |
| Test Cases | Detailed manual test cases |
| Bug Reports | Documented defects |
| API Collection | Postman API testing |
| Regression Results | Test execution results |

---

# Test Results

| Metric | Result |
|--------|--------|
| Total Test Cases | 97 |
| Passed | 68 |
| Failed | 13 |
| Bugs Found | 16 |

**Pass Rate:** 70%
---

# Known Issues

Examples of bugs found during testing:

- Admin cannot edit product due to inactive button
- Price field accepts invalid input
- Some product descriptions are not localized
- Missing validation on review form

Detailed reports are available in the **Bug Reports** section.

---

# Project Structure

```
StyleHub-QA-Testing
│
├── Test-Plan
│
├── Test-Cases
│
├── Bug-Reports
│
├── API-Testing


---
