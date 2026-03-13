Bug Reports
C51 – Profile Name Is Not Updated Despite Successful API Response

Priority: Medium

Preconditions

User account exists

User is logged in

Profile page is accessible

Steps to Reproduce

Login to the application

Navigate to Profile page

Enter a new valid Name value

Click Save

Refresh the page

Expected Result

Name should be updated in the database

Updated value should persist after page refresh

API response should reflect the actual updated data

Actual Result

API request is sent successfully

Server responds with 200 { success: true, user: {...} }

Name remains unchanged after page refresh

Database does not reflect the updated value

C64 – User Can Add Out-of-Stock Product to Cart

Priority: High

Preconditions

User is on the store page

There is a product marked as Out of Stock

Steps to Reproduce

Go to Product page

Locate a product labeled Out of Stock

Click Add to Cart

Expected Result

Add to Cart button should be disabled

User should not be able to add the product to the cart

Optional message: "Product is out of stock"

Actual Result

User can add an out-of-stock product to the cart

Cart updates even though the product is unavailable

C67 – Duplicate Product Is Added Multiple Times to Favourites

Priority: Medium

Preconditions

User is logged in

User is on the product page or product listing

Steps to Reproduce

Go to Product page

Click Add to Favourites

Click Add to Favourites again for the same product

Expected Result

Product should appear only once in the favourites list

Duplicate entries should be prevented

Actual Result

The same product appears multiple times in favourites

C93 – All Errors Return 500 Status Code

Priority: Medium

Steps to Reproduce

Send request with missing fields → returns 500 instead of 400

Request a non-existent resource → returns 500 instead of 404

Access protected endpoint without authorization → returns 500 instead of 401

Expected Result

Each error should return the appropriate HTTP status code:

400 – Bad Request

401 – Unauthorized

404 – Not Found

Actual Result

All error scenarios return 500 Internal Server Error

C95 – Duplicate Cart Items Instead of Quantity Increment

Priority: Medium

Preconditions

Product is in stock

User is on the product page

Steps to Reproduce

Click Add to Cart for a product

Open the cart and note the quantity

Click Add to Cart again for the same product

Expected Result

Only one cart entry per product

Quantity should increase with each addition

Cart total should update accordingly

Actual Result

A new cart row is created each time

Quantity does not increment

Duplicate cart entries appear

C97 – Empty Cart Can Proceed to Payment

Priority: Medium

Preconditions

User is on the Cart page

Cart is empty

Steps to Reproduce

Open the cart page

Verify the cart contains no products

Click Proceed to Payment

Expected Result

Button should be disabled

User should not reach the payment page

Message should inform that the cart is empty

Actual Result

User can proceed to Payment page with an empty cart

C98 – No Visual Feedback for Add to Favourites

Priority: Medium

Preconditions

User is logged in

User is on product page or product grid

Steps to Reproduce

Locate a product

Click Add to Favourites

Expected Result

User receives visual confirmation:

Heart icon changes color

Tooltip or message appears

Action confirmation is visible

Actual Result

No visual feedback is shown

User cannot confirm if the item was added

C99 – Password Change Without Matching Validation

Priority: Medium

Steps to Reproduce

Go to Profile page

Enter different values in New Password and Confirm Password

Submit the form

Expected Result

Form should validate that passwords match

Submission should be blocked if they differ

Actual Result

Mismatched passwords are accepted

Request is sent without validation

C100 – Sort by Price High to Low Returns Same as Low to High

Priority: Medium

Preconditions

Product list contains items with different prices

Steps to Reproduce

Sort products Price: Low → High

Note the order

Sort products Price: High → Low

Expected Result

Products should be displayed from highest to lowest price

Actual Result

Order remains identical to Low → High sorting

C105 – No Card Number Validation on Payment

Priority: Medium

Preconditions

User has items in cart

User is on payment page

Steps to Reproduce

Enter letters in card number field

Enter incorrect length

Submit payment

Expected Result

Only digits allowed

Card number length validation

Payment should fail with validation message

Actual Result

Any input is accepted

Payment is processed successfully

C116 – Payment Is Processed with Invalid Price Input

Priority: Medium

Preconditions

User has items in cart

User is on checkout page

Steps to Reproduce

Manipulate price value (via UI or DevTools)

Examples:

Negative value -50

Text input "abc123"

Extremely large number

Click Pay Now

Expected Result

System should validate price value

Invalid input should be rejected

Payment should not be processed

Actual Result

Payment is processed successfully

Order created with invalid price data

C121 – Admin Unable to Edit Existing Product

Priority: Medium

Preconditions

Admin user logged in

At least one product exists

Steps to Reproduce

Login as Admin

Open Admin Dashboard → Products

Select existing product

Click Edit

Expected Result

Product edit form should open

Admin should be able to modify product details

Actual Result

Clicking Edit does nothing

No modal or form appears

C128 – Untranslated Button Text in Ukrainian

Priority: Medium

Preconditions

Ukrainian language selected

Steps to Reproduce

Switch language to Ukrainian

Open any product page

Expected Result

Button should display:

Додати до кошика
Actual Result

Button shows placeholder:

[TRANSLATE_ME]
C129 – Product Description in Wrong Language

Priority: Medium

Steps to Reproduce

Select English language

Locate product Windbreaker Sport Jacket

Expected Result

Description should be displayed in English

Actual Result

Description appears in Ukrainian

C130 – Product Title and Description Not Translated to Ukrainian

Priority: Medium

Preconditions

Website supports UA / ENG language switch

Steps to Reproduce

Switch language to Ukrainian

Open product page

Expected Result

Product title translated into Ukrainian

Product description translated into Ukrainian

Actual Result

Title remains in English

Description remains in English

Only interface elements are translated
