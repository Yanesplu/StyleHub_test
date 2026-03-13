# Bug Reports

Collection of defects discovered during manual testing of the **StyleHub e-commerce application**.

---

## C51 — Profile Name Is Not Updated Despite Successful API Response

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Profile |
| Type | Functional |

### Preconditions
- User account exists
- User is logged in
- Profile page is accessible

### Steps to Reproduce
1. Login to the application
2. Navigate to **Profile page**
3. Enter a new valid **Name**
4. Click **Save**
5. Refresh the page

### Expected Result
- Name should be updated in the database
- Updated value should persist after refresh
- API response should reflect updated data

### Actual Result
- API request returns **200 OK**
- Response body contains `{ success: true }`
- Name remains unchanged after refresh
- Database value is not updated

---

## C64 — User Can Add Out-of-Stock Product to Cart

| Field | Value |
|------|------|
| Priority | High |
| Component | Cart |
| Type | Functional |

### Preconditions
- User is on the store page
- Product is marked **Out of Stock**

### Steps to Reproduce
1. Open **Product page**
2. Locate a product labeled **Out of Stock**
3. Click **Add to Cart**

### Expected Result
- Button should be **disabled**
- Product should not be added to cart
- Optional message: *Product is out of stock*

### Actual Result
- Product is added to the cart
- Cart updates despite unavailable stock

---

## C67 — Duplicate Product Added to Favourites

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Favourites |
| Type | Functional |

### Preconditions
- User is logged in
- User is on product page

### Steps to Reproduce
1. Open **Product page**
2. Click **Add to Favourites**
3. Click **Add to Favourites** again

### Expected Result
- Product should appear **only once** in favourites

### Actual Result
- Same product appears **multiple times**

---

## C93 — All Errors Return 500 Status Code

| Field | Value |
|------|------|
| Priority | Medium |
| Component | API |
| Type | API |

### Steps to Reproduce
1. Send request with **missing fields**
2. Request **non-existent resource**
3. Access **protected endpoint without authorization**

### Expected Result
Proper HTTP status codes should be returned:

| Scenario | Expected Code |
|--------|--------|
| Invalid request | 400 |
| Unauthorized access | 401 |
| Resource not found | 404 |

### Actual Result
All requests return:

```
500 Internal Server Error
```

---

## C95 — Duplicate Cart Items Instead of Quantity Increment

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Cart |
| Type | Functional |

### Preconditions
- Product is in stock
- User is on product page

### Steps to Reproduce
1. Click **Add to Cart**
2. Open cart
3. Click **Add to Cart** again

### Expected Result
- Only **one cart entry per product**
- Quantity should **increase**
- Cart total updates correctly

### Actual Result
- Multiple duplicate rows appear
- Quantity does not increment

---

## C97 — Empty Cart Can Proceed to Payment

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Checkout |
| Type | Functional |

### Preconditions
- Cart is empty

### Steps to Reproduce
1. Open cart page
2. Click **Proceed to Payment**

### Expected Result
- Checkout button should be **disabled**
- User should not reach payment page

### Actual Result
- User can proceed to payment with empty cart

---

## C98 — No Visual Feedback When Adding to Favourites

| Field | Value |
|------|------|
| Priority | Medium |
| Component | UI |
| Type | UI |

### Preconditions
- User is logged in
- Product page is open

### Steps to Reproduce
1. Click **Add to Favourites**

### Expected Result
User should see confirmation:

- Heart icon changes color
- Tooltip appears
- Notification displayed

### Actual Result
- No visual confirmation is shown

---

## C99 — Password Change Without Matching Validation

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Profile |
| Type | Validation |

### Steps to Reproduce
1. Open **Profile page**
2. Enter different values in:
   - New Password
   - Confirm Password
3. Submit form

### Expected Result
- Passwords must match before submission

### Actual Result
- Form submits mismatched passwords

---

## C100 — Price Sorting High to Low Does Not Work

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Search |
| Type | Functional |

### Steps to Reproduce
1. Sort products **Low → High**
2. Sort products **High → Low**

### Expected Result
Products should display **highest price first**

### Actual Result
Sorting order remains identical to **Low → High**

---

## C105 — No Card Number Validation on Payment

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Payment |
| Type | Validation |

### Preconditions
- Product added to cart
- User on payment page

### Steps to Reproduce
1. Enter letters in card number
2. Enter invalid length
3. Submit payment

### Expected Result
- Only numeric input allowed
- Card number length validation
- Payment should fail

### Actual Result
Payment succeeds with invalid card number

---

## C116 — Payment Processed with Invalid Price

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Payment |
| Type | Security |

### Steps to Reproduce
1. Manipulate price value (DevTools)
2. Enter:
   - negative price
   - text value
   - extremely large number
3. Click **Pay Now**

### Expected Result
Payment should be blocked with validation error.

### Actual Result
Payment succeeds and order is created.

---

## C121 — Admin Cannot Edit Existing Product

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Admin |
| Type | Functional |

### Preconditions
- Admin logged in
- Products exist

### Steps to Reproduce
1. Open **Admin Dashboard**
2. Navigate to **Products**
3. Click **Edit**

### Expected Result
Product edit form should open.

### Actual Result
Clicking **Edit** produces no action.

---

## C128 — Untranslated Button Text in Ukrainian

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Localization |
| Type | UI |

### Steps to Reproduce
1. Switch language to **Ukrainian**
2. Open product page

### Expected Result

```
Додати до кошика
```

### Actual Result

```
[TRANSLATE_ME]
```

---

## C129 — Product Description in Wrong Language

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Localization |
| Type | UI |

### Steps to Reproduce
1. Select **English language**
2. Open product **Windbreaker Sport Jacket**

### Expected Result
Description should be in **English**

### Actual Result
Description is displayed in **Ukrainian**

---

## C130 — Product Title and Description Not Translated to Ukrainian

| Field | Value |
|------|------|
| Priority | Medium |
| Component | Localization |
| Type | UI |

### Steps to Reproduce
1. Switch language to **Ukrainian**
2. Open product page

### Expected Result
Product title and description translated to Ukrainian.

### Actual Result
Product content remains in English.
