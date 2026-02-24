# StyleHub_test
Test Plan
Project: Internet Clothes Shop (Next.js + PostgreSQL)
1. Objective
The objective of this test plan is to verify functionality, stability, and security of the Internet Clothes Shop web application built with Next.js and PostgreSQL (raw SQL queries).
The testing covers UI, API, database validation, localization, and basic security checks.

2. Scope
In Scope:
Multi-language support (UA / ENG)
User Registration & Login
Profile management
Product catalog
Product details page
Reviews functionality
Search functionality
Cart functionality
Mock payment process
Admin dashboard
REST API endpoints
Database validation (PostgreSQL)
Console logging validation

Out of Scope:
Performance testing
Load testing
Real payment gateway integration
Advanced security penetration testing

3. Tech Stack
Frontend: Next.js
Backend: Next.js API Routes
Database: PostgreSQL
Queries: Raw SQL
Testing Tools:
Browser DevTools
Swagger / Postman
TestRail

4. Test Types
Functional Testing
Regression Testing
UI Testing
API Testing
Database Testing
Localization Testing
Basic Security Testing (SQL Injection)
Console Logging Validation

5. Test Environment
OS: Windows 11
Browser: Google Chrome
Database: PostgreSQL (local)
API tested via Swagger and Postman

6. Features to be Tested
6.1 General
Header and Footer layout
Navigation
Language switching
Console logs validation

6.2 Authentication
Registration
Email mock verification
Login / Logout
Session persistence
Access control

6.3 Profile
Update name
Change password
View favourites
View order history

6.4 Product Management
View products
Add to cart
Add to favourites
Add reviews

6.5 Search
Search by product title
Partial match
No results scenario

6.6 Cart
Add / remove products
Quantity update
Total calculation

6.7 Payment
Mock payment process
Order creation in DB

6.8 Admin Dashboard
Create product
Update product
Manage users
Change user role
View orders

6.9 API Testing
Status code validation
Response body validation
Authorization checks
Negative testing

6.10 Database Testing
Data insertion validation
Data update validation
SQL injection checks
Data integrity validation

7. Risks
Raw SQL queries may cause SQL injection vulnerabilities
Localization may have missing translations
Console logs may expose sensitive data
Role-based access may have incorrect permissions

8. Entry Criteria
Application deployed locally
Database connected
All main features implemented

9. Exit Criteria
All critical test cases executed
No critical or high severity defects open
Core functionality works correctly

10. Deliverables
Test Plan
Test Cases
Bug Reports

API Collection (Postman)
Regression Test Results
