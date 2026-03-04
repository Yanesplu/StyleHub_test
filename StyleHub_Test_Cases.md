# StyleHub Test Cases

------------------------------------------------------------------------

## C38 - Verify successful user registration with valid data

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on Registration page

### Steps

1.  Enter valid name2. Enter valid email3. Enter valid password4. Select
    role "user"5. Submit form6. Verify record in database using SQL
    queryTest Data: a@mail.com

### Expected Result

User account is successfully created and system redirects user to Login
page.User record created in DB

------------------------------------------------------------------------

## C39 - Verify mock email verification redirects to login

**Type:** Functional

**Priority:** Medium

### Preconditions

User completed registration

### Steps

1.  Enter any verification code2. Submit

### Expected Result

Account is verified and user is redirected to Login page.

------------------------------------------------------------------------

## C40 - Verify registration fails with empty required fields

**Type:** Functional

**Priority:** Medium

### Preconditions

Registration page opened

### Steps

1.  Leave fields empty2. Click Submit

### Expected Result

Validation errors are displayed.

------------------------------------------------------------------------

## C41 - Verify registration fails with invalid email format

**Type:** Functional

**Priority:** Medium

### Preconditions

Registration page opened

### Steps

1.  Enter invalid email (example@)2. Fill other fields correctly3.
    Submit

### Expected Result

Error message about invalid email format is displayed.

------------------------------------------------------------------------

## C42 - Verify registration fails with already existing email

**Type:** Other

**Priority:** Medium

### Preconditions

User with email already exists in DB

### Steps

1.  Enter existing email2. Fill other fields3. Submit

### Expected Result

System displays "Email already exists" error.

------------------------------------------------------------------------

## C43 - Verify successful login with valid credentials

**Type:** Functional

**Priority:** Medium

### Preconditions

User is registered

### Steps

1.  Enter correct email2. Enter correct password3. Click Login

### Expected Result

User is logged in and redirected to Home page.

------------------------------------------------------------------------

## C44 - Verify login fails with incorrect password

**Type:** Functional

**Priority:** Medium

### Preconditions

User exists

### Steps

1.  Enter correct email2. Enter wrong password3. Click Login

### Expected Result

Error message is displayed.

------------------------------------------------------------------------

## C45 - Verify login fails with non-existing email

**Type:** Other

**Priority:** Medium

### Preconditions

Login page opened

### Steps

1.  Enter unregistered email2. Enter password3. Click Login

### Expected Result

Error message is displayed.

------------------------------------------------------------------------

## C46 - Verify SQL injection attempt in login field

**Type:** Other

**Priority:** Medium

### Preconditions

Login page opened

### Steps

1.  Enter ' OR 1=1 -- in email field2. Enter random password3. Click
    Login

### Expected Result

Login fails and system does not authenticate user.

------------------------------------------------------------------------

## C47 - Verify logout functionality

**Type:** Other

**Priority:** Medium

### Preconditions

User logged in

### Steps

Click Sign Out

### Expected Result

User is logged out and redirected to Home page.

------------------------------------------------------------------------

## C57 - Verify favourites list updates after removing product

**Type:** Other

**Priority:** Medium

### Preconditions

User logged inAt least 1 product in favourites

### Steps

1.  Open Favourites section2. Remove one product from favourites3.
    Refresh page

### Expected Result

Removed product is no longer displayed

------------------------------------------------------------------------

## C48 - Verify authorized user can access Profile page

**Type:** Other

**Priority:** Medium

### Preconditions

Test Data:Email: testuser@example.comPassword: ValidPass1231. User
account exists in database2. User is logged in

### Steps

1.  Login with valid credentials2. Click on "Profile" link in header

### Expected Result

1.  User is redirected to /profile page. User information is displayed

------------------------------------------------------------------------

## C49 - Verify unauthorized user cannot access Profile page

**Type:** Other

**Priority:** Medium

### Preconditions

User is logged out

### Steps

1.  Manually enter /profile URL in browser2. Press Enter

### Expected Result

System redirects user to Login pageProfile data is not displayed

------------------------------------------------------------------------

## C50 - Verify user can successfully update Name

**Type:** Other

**Priority:** Medium

### Preconditions

User logged inNew Name: Noname

### Steps

1.  Open Profile page2. Change Name field3. Click Save4. Refresh page

### Expected Result

1.  Success response is returned from API  2. Name is updated in UI3.
    Database contains updated Name value

------------------------------------------------------------------------

## C52 - Verify user cannot save empty name

**Type:** Other

**Priority:** Medium

### Preconditions

Profile page opened

### Steps

1.  Clear Name field2. Click Save

### Expected Result

Validation error is displayed and data is not updated.

------------------------------------------------------------------------

## C53 - Verify user can change password successfully

**Type:** Other

**Priority:** Medium

### Preconditions

User logged incurrent password: 12345new: 123456

### Steps

1.  Enter correct current password2. Enter new password3. Confirm new
    password4. Click Save5. Logout6. Login with new password

### Expected Result

Password update request returns success statusOld password no longer
works

------------------------------------------------------------------------

## C54 - Verify password change fails with incorrect current password

**Type:** Other

**Priority:** Medium

### Preconditions

User logged in

### Steps

1.  Enter incorrect current password2. Enter new password3. Click Save

### Expected Result

System displays error messagePassword is not changed

------------------------------------------------------------------------

## C55 - Verify user can view favourite

**Type:** Other

**Priority:** Medium

### Preconditions

1.  User account exists2. User logged in3. At least 1 product added to
    favourites

### Steps

1.  Open home page2. Click to product3. Add to favorite4. Click to User
    page5. Open "Favourites" section

### Expected Result

List of favourite products is displayed

------------------------------------------------------------------------

## C56 - Verify empty favourites state is handled correctly

**Type:** Other

**Priority:** Medium

### Preconditions

User logged inUser has no favourite products

### Steps

1.  Navigate to Profile page2. Open "Favourites" section

### Expected Result

System displays message like: "No favourite products yet"No errors
appear in console

------------------------------------------------------------------------

## C58 - Verify user can view order history

**Type:** Other

**Priority:** Medium

### Preconditions

User logged inAt least one completed order exists in database

### Steps

1.  Login2. Navigate to Profile page3. Open "Orders" section

### Expected Result

List of previous orders is displayedEach order contains:-Order
ID-Date-Total amount-List of purchased products

------------------------------------------------------------------------

## C59 - Verify empty order history is handled correctly

**Type:** Other

**Priority:** Medium

### Preconditions

User logged inNo orders in database

### Steps

1.  Navigate to Profile page2. Open Orders section

### Expected Result

Message displayed: "No orders yet"

------------------------------------------------------------------------

## C51 - \[BUG\] C50 Profile name is not updated despite successful API response

**Type:** Other

**Priority:** Medium

### Preconditions

1.  User account exists2. User is logged in3. Profile page is accessible

### Steps

Steps to Reproduce1.Login to the application2. Navigate to Profile
page3. Enter new valid Name value4. Click "Save"5. Refresh the page

### Expected Result

Actual Result-API request is sent successfully-Server responds with 200
{ success: true, user: {...} }-Name remains unchanged after page
refresh-Database does not reflect updated valueExpected Result-Name
should be updated in the database-Updated value should persist after
page refresh-API response should reflect actual updated data

------------------------------------------------------------------------

## C64 - \[BUG\] C63 User can add out-of-stock product to cart

**Type:** Other

**Priority:** High

### Preconditions

User is on the store page.There is a product marked as "Out of Stock."

### Steps

Steps to Reproduce:1. Go to Product page2. Locate a product labeled "Out
of Stock"3. Click the "Add to Cart" button

### Expected Result

Expected Result:-The "Add to Cart" button should be disabled or the user
should not be able to add the product to the cart.-If applicable, a
message like "Product is out of stock" should appear.Actual Result:-The
user is able to add the out-of-stock product to the cart.-The cart
updates with the product even though it is not available.

------------------------------------------------------------------------

## C67 - \[BUG\] C66 Duplicate product is added multiple times to favourites

**Type:** Other

**Priority:** Medium

### Preconditions

User is logged in (if required).User is on the product listing or
product detail page.

### Steps

Steps to Reproduce:Go to Product pageLocate a productClick the "Add to
Favorites" button for that productClick the "Add to Favorites" button
again for the same product

### Expected Result

Expected Result:-The product should appear only once in the Favorites
list.-Duplicate entries should be prevented.Actual Result:-The same
product is added multiple times to the Favorites list.

------------------------------------------------------------------------

## C76 - \[BUG\] C75 carousel click action is not redirected to the correct page or link associated with the carousel image

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C93 - \[BUG\] C71 All Errors Return 500 Status Code

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Steps to Reproduce:1. Send a request with missing fields --- returns 500
instead of 4002. Request a non-existent resource --- returns 500 instead
of 4043. Access protected endpoint without auth --- returns 500 instead
of 401

### Expected Result

Expected: Appropriate HTTP status codes for each error typeActual:
Everything returns 500

------------------------------------------------------------------------

## C95 - \[BUG\] C94 Duplicate Cart Items Instead of Incrementing

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the product page or product grid.Product is in stock.Cart may
be empty or contain other products.

### Steps

1.  Click "Add to Cart" on a specific product (e.g., "Blue T-Shirt").2.
    Open the cart and note the quantity of the product.3. Click "Add to
    Cart" again for the same product.4. Repeat multiple times if needed.

### Expected Result

Expected Result: -Only one cart entry exists per product. -Quantity
increments with each addition.-Cart total updates correctly based on
quantity × price. Actual Result: -A new cart row is created each time
the same product is added. -Quantity does not increment; -multiple
duplicate entries appear in the cart. -Cart total may be incorrect or
misleading.

------------------------------------------------------------------------

## C97 - \[BUG\] C96 Empty Cart Can Proceed to Payment

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the cart page.Cart is empty.

### Steps

1.  Open the cart page.2. Verify that the cart has no products.3. Click
    the "Proceed to Payment" or "Checkout" button.

### Expected Result

Expected Result: -The button should be disabled.-User should not reach
the payment page. -Appropriate message should inform the user that the
cart is empty. Actual Result: -User is able to click "Proceed to
Payment".-Payment page opens even though the cart has no items.

------------------------------------------------------------------------

## C98 - \[BUG\] No Visual Feedback for Add to Favourites

**Type:** Other

**Priority:** Medium

### Preconditions

User is logged in (if required).User is on a product page or product
grid.

### Steps

1.  Locate a product on the product grid or product detail page.2. Click
    the "Add to Favourites" button (heart icon or similar).

### Expected Result

Expected Result:- User receives visual feedback, e.g.,: -Heart icon
changes color or fills in.- A tooltip or message appears: "Added to
Favourites".- Feedback confirms the action was successful. Actual
Result: -No visual feedback is shown. -User cannot tell if the product
was added to favourites.

------------------------------------------------------------------------

## C99 - \[BUG\] Password Change Without Matching Validation

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Go to profile page2. Enter different values in "New Password" and
    "Confirm New Password"3. Submit --- request is sent without
    client-side validation

### Expected Result

Expected:- Form should validate matching passwords before
submissionActual: -Mismatched passwords are accepted and submitted

------------------------------------------------------------------------

## C100 - \[BUG\] C83,84 Sort by Price High to Low Returns Same as Low to High

**Type:** Other

**Priority:** Medium

### Preconditions

User is on a product listing page with multiple products.Products have
varying prices.

### Steps

1.  On home page, sort by "Price: Low to High" --- note order2. Sort by
    "Price: High to Low" --- same order

### Expected Result

Expected Result: -"Price: High to Low" should display products from
highest to lowest price.- Order should be opposite of "Low to
High".Actual Result: -"Price: High to Low" displays products in the same
order as "Low to High". -Sorting does not change the order as expected.

------------------------------------------------------------------------

## C105 - \[BUG\] C103 No Card Number Validation on Payment

**Type:** Other

**Priority:** Medium

### Preconditions

User has at least one product in the cart.User is on the
Payment/Checkout page.

### Steps

1.  Go to payment page2. Enter letters in card number field ---
    accepted3. Enter any length --- accepted4. Submit --- payment
    "succeeds"

### Expected Result

Expected:Card number should only accept digits, enforce length, and
validate formatActual: Any text input is accepted

------------------------------------------------------------------------

## C116 - \[BUG\] C115 Payment Is Processed with Invalid Price Input

**Type:** Other

**Priority:** Medium

### Preconditions

User has at least one product in the cartUser is on the Payment/Checkout
page

### Steps

1.  Proceed to the Payment page.2. Manipulate the price value (if
    editable via UI or DevTools), or enter invalid price data if the
    field is available.Examples:-Negative value (e.g., -50)-Text input
    (e.g., "abc123")-Extremely large number3. Complete other required
    fields with valid data.4. Click "Pay Now".

### Expected Result

Expected Result:-System should validate the price value.-Invalid price
inputs should be rejected.-Payment should not be processed.-Appropriate
error message should be displayed.Actual Result:-Payment is successfully
processed despite invalid price input.-No validation error is
shown.-Order is created with incorrect price data.

------------------------------------------------------------------------

## C121 - \[BUG\] Admin Unable to Edit Existing Product

**Type:** Other

**Priority:** Medium

### Preconditions

Admin user is logged inAt least one product exists in the systemAdmin is
on the Admin Dashboard

### Steps

1.  Log in as Admin.2. Navigate to the "Products" section.3. Select an
    existing product.4. Click the "Edit" button.

### Expected Result

Expected Result:-Edit product form should open.-Admin should be able to
modify product details.Actual Result:-Clicking the "Edit" button
produces no action.-No modal opens.-No error message is displayed.

------------------------------------------------------------------------

## C128 - \[BUG\] Untranslated Button Text in Ukrainian

**Type:** Other

**Priority:** Medium

### Preconditions

The Ukrainian translation for the "Add to Cart" button is incorrect ---
uses a placeholder \[TRANSLATE_ME\] value.

### Steps

1.  Switch language to Ukrainian2. Navigate to any product page3. "Add
    to Cart" button shows \[TRANSLATE_ME\]

### Expected Result

Expected: Should show "Додати до кошика"Actual: Shows \[TRANSLATE_ME\]

------------------------------------------------------------------------

## C129 - \[BUG\] Product Description in Wrong Language

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Browse products with English language selected2. Find "Windbreaker
    Sport Jacket" --- description is in Ukrainian

### Expected Result

Expected: All product descriptions should be in the selected
languageActual: One description is hardcoded in Ukrainian

------------------------------------------------------------------------

## C130 - \[BUG\] Product Title and Description Are Not Translated to Ukrainian

**Type:** Other

**Priority:** Medium

### Preconditions

Website supports language switch (UA / ENG).User is on any product
listing page or product detail page.

### Steps

1.  Open the website.2. Switch language to Ukrainian (UA).3. Navigate to
    a product page or view products in product grid.4. Check product
    title and description.

### Expected Result

Expected Result:-Product title is translated into Ukrainian.-Product
description is translated into Ukrainian.-No English text remains after
switching language.Actual Result:-Product title remains in
English.-Product description remains in English.-Only interface elements
are translated, but product content is not.

------------------------------------------------------------------------

## C60 - Verify product page loads correctly

**Type:** Other

**Priority:** High

### Preconditions

Product exists in database

### Steps

1.  Navigate to Home page2. Click on any product

### Expected Result

Product page opens successfullyCorrect product information is
displayedNetwork request returns 200

------------------------------------------------------------------------

## C61 - Verify product details match database records

**Type:** Other

**Priority:** Medium

### Preconditions

Product exists in DB

### Steps

1.  Open Product page2. Compare displayed data with database values

### Expected Result

Title matches DBDescription matches DBPrice matches DBAvailable quantity
matches DB

------------------------------------------------------------------------

## C62 - Verify user can add product to cart

**Type:** Other

**Priority:** Medium

### Preconditions

User logged inProduct in stock

### Steps

1.  Open Product page2. Click "Add to Cart"

### Expected Result

Product added to cartCart counter updatesAPI returns successProduct
appears in Cart page

------------------------------------------------------------------------

## C63 - Verify user cannot add out-of-stock product to cart

**Type:** Other

**Priority:** Medium

### Preconditions

Product quantity = 0

### Steps

1.  Open Product page2. Click "Add to Cart"

### Expected Result

Add action blockedProper message displayedNo incorrect order created

------------------------------------------------------------------------

## C65 - Verify user can add product to favourites

**Type:** Other

**Priority:** Medium

### Preconditions

User logged in

### Steps

1.  Open Product page2. Click "Add to Favourites"3. Click to Profile
    page4. Click "Favourites"

### Expected Result

Product added to favouritesIcon changes stateProduct appears in Profile
→ Favourites

------------------------------------------------------------------------

## C66 - Verify duplicate product is not added multiple times to favourites

**Type:** Other

**Priority:** Medium

### Preconditions

Product already in favourites

### Steps

Click "Add to Favourites" again

### Expected Result

Product not duplicatedNo duplicate entry in DB

------------------------------------------------------------------------

## C68 - Verify product reviews are displayed

**Type:** Other

**Priority:** Medium

### Preconditions

Product has reviews in DB

### Steps

1.  Open Product page2. Scroll to Reviews section

### Expected Result

All reviews are displayedEach review shows:-User name-Rating-Comment

------------------------------------------------------------------------

## C69 - Verify user can add review to product

**Type:** Other

**Priority:** Medium

### Preconditions

User logged in

### Steps

1.  Open Product page2. Enter review text3. Select rating4. Submit
    review

### Expected Result

Review successfully savedReview appears in list after refreshAPI returns
201 DB contains new review record

------------------------------------------------------------------------

## C70 - Verify unauthorized user cannot add review

**Type:** Other

**Priority:** Medium

### Preconditions

User logged out

### Steps

1.  Open Product page2. Attempt to submit review

### Expected Result

User redirected to LoginORLogin to wtire a reviewReview not saved in DB

------------------------------------------------------------------------

## C71 - Verify invalid product ID returns error page

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Manually enter invalid product ID in URL

### Expected Result

Product not foundAPI returns 404No application crashNo sensitive data
exposed

------------------------------------------------------------------------

## C72 - Verify carousel visibility

**Type:** Other

**Priority:** Medium

### Preconditions

User is on Home Page

### Steps

1.  Open Home Page2. Observe the hero carousel at the top of the page

### Expected Result

Carousel is visible and properly displayed

------------------------------------------------------------------------

## C73 - Verify carousel navigation (next/previous)

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Click the "Next" arrow on the carousel2. Click the "Previous" arrow

### Expected Result

Carousel slides to the next and previous images correctly

------------------------------------------------------------------------

## C74 - Verify carousel auto-slide

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Wait for the carousel to auto-slide

### Expected Result

Carousel automatically transitions to the next image after the set
interval

------------------------------------------------------------------------

## C75 - Verify carousel click action

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Click on a carousel image

### Expected Result

User is redirected to the correct page or link associated with the
carousel image

------------------------------------------------------------------------

## C77 - Verify products are displayed

**Type:** Other

**Priority:** Medium

### Preconditions

Product page is open

### Steps

Scroll to the product grid section

### Expected Result

All products in the grid are displayed with image, name, price, and
action buttons

------------------------------------------------------------------------

## C78 - Verify product details link

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C79 - Verify ""Add to Cart"" button

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C80 - Verify ""Add to Favorites"" button

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C81 - Verify pagination buttons visibility

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C82 - Verify page navigation

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Click a page number2. Click "Next" button3. Click "Previous" button

### Expected Result

Product grid updates according to the selected page

------------------------------------------------------------------------

## C83 - Verify sorting by price (Low to High)

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C84 - Verify sorting by price (High to Low)

**Type:** Other

**Priority:** Medium

### Preconditions

Open Product page

### Steps

### Expected Result

------------------------------------------------------------------------

## C85 - Verify sorting by price range \$0--\$500

**Type:** Other

**Priority:** Medium

### Preconditions

User is on Home Page.Products have prices that include values below \$0,
exactly \$0, between \$0--\$500, exactly \$500, and above \$500.

### Steps

### Expected Result

------------------------------------------------------------------------

## C86 - Verify sorting by category

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------

## C87 - Search by Title

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the category or home page

### Steps

1.  Enter full product title in search bar (e.g., "Blue Cotton
    T-Shirt")2. Click Search / press Enter

### Expected Result

Only product(s) with exact title are displayedNo unrelated products are
shown

------------------------------------------------------------------------

## C88 - Verify search handles no matching results correctly

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the category or home page

### Steps

1.  Enter a non-existing product name (Red Unicorn Jacket)2. Click
    Search / press Enter

### Expected Result

No products are displayedA message like "No products found" appearsPage
layout remains correct

------------------------------------------------------------------------

## C89 - Verify search returns products that partially match input

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the category or home page

### Steps

1.  Enter a partial product title (e.g., "Cotton")2. Click Search /
    press Enter

### Expected Result

All products containing the input text in their title are
displayedProducts without the partial word are not displayed

------------------------------------------------------------------------

## C90 - Verify user can add a product to the cart

**Type:** Other

**Priority:** Medium

### Preconditions

User is on a product page or product grid; product is in stock

### Steps

1.  Click "Add to Cart" on a product2. Open "Cart"

### Expected Result

Product is added to the cartCart count updates correctlyProduct details
(name, price, quantity) are correct in the cart

------------------------------------------------------------------------

## C91 - Verify user can remove a product from the cart

**Type:** Other

**Priority:** Medium

### Preconditions

Cart has at least one product

### Steps

1.  Open the cart2. Click "Remove" on a product

### Expected Result

Product is removed from the cartCart count updates correctlyCart total
updates correctly

------------------------------------------------------------------------

## C92 - Verify cart total calculation is correct

**Type:** Other

**Priority:** Medium

### Preconditions

Cart has one or more products

### Steps

1.  Add multiple products to the cart with known prices2. Observe the
    total price displayed in the cart3. Change quantity of one product
    and observe the updated total4. Remove a product and check the
    updated total

### Expected Result

Total price equals the sum of all product prices × quantitiesUpdates
correctly when quantities change or products are removedNo rounding or
calculation errors

------------------------------------------------------------------------

## C94 - Verify Items in Cart Increment Instead of Duplicate

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the product page or product grid.Cart may be empty or have
other products.Product is in stock.

### Steps

1.  Click "Add to Cart" on a specific product (e.g., "Blue T-Shirt").2.
    Open the cart and note the quantity of that product.3. Click "Add to
    Cart" again for the same product.4. Repeat for a few more times if
    needed

### Expected Result

The cart shows only one entry for that product. The quantity increments
with each addition  No duplicate product rows appear in the cart.

------------------------------------------------------------------------

## C96 - Verify empty cart cannot Proceed to Payment

**Type:** Other

**Priority:** Medium

### Preconditions

User is on the website.Cart is empty.

### Steps

1.  Open the cart page.2. Verify that the cart has no products.3.
    Attempt to click "Proceed to Payment" or "Checkout".

### Expected Result

The "Proceed to Payment" button should be disabled or unclickable. If
clicked, a message should appear: "Your cart is empty" or similar. User
cannot access payment page until at least one product is added.

------------------------------------------------------------------------

## C101 - Verify mock payment flow works correctly

**Type:** Other

**Priority:** Medium

### Preconditions

User has at least one product in cartUser is on Checkout/Payment page

### Steps

1.  Proceed to Payment page2. Enter valid mock payment details3. Click
    "Pay Now"

### Expected Result

Payment request is processedUser is redirected to confirmation/success
pageOrder is created successfully

------------------------------------------------------------------------

## C102 - Verify successful payment scenario

**Type:** Other

**Priority:** Medium

### Preconditions

Cart contains productsUser is on Payment page

### Steps

1.  Enter valid card details2. Confirm payment3. Wait for response

### Expected Result

Payment is successfulSuccess message appearsOrder confirmation page is
displayedCart is clearedOrder ID is generated

------------------------------------------------------------------------

## C103 - Verify system handles failed payment properly

**Type:** Other

**Priority:** Medium

### Preconditions

Enter invalid or declined card detailsClick "Pay Now"

### Steps

1.  Enter invalid or declined card details2. Click "Pay Now"

### Expected Result

Payment is declinedError message appears (e.g., "Payment Failed" or
"Card Declined")User remains on payment pageCart is NOT clearedUser can
retry payment

------------------------------------------------------------------------

## C104 - Verify required field validation

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Leave required fields empty2. Click "Pay Now"

### Expected Result

Validation errors appearPayment is not processed

------------------------------------------------------------------------

## C106 - Verify card number format validation

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Enter invalid card number (e.g., letters or too short number)2.
    Click "Pay Now"

### Expected Result

Validation error appearsPayment is not processed

------------------------------------------------------------------------

## C107 - Verify expired card cannot be used

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Enter expired expiration date2. Click "Pay Now"

### Expected Result

Error message appearsPayment is blocked

------------------------------------------------------------------------

## C108 - Verify system stability during refresh

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Start payment process2. Refresh page

### Expected Result

No duplicate charge occursSystem handles session correctly

------------------------------------------------------------------------

## C109 - Verify admin can create a new product

**Type:** Other

**Priority:** Medium

### Preconditions

Admin is logged inAdmin is on Dashboard page

### Steps

1.  Navigate to "Products" section2. Click "Create Product" / "Add
    Product"3. Fill in all required fields (Title, Price, Category,
    Description, Image, Stock)4. Click "Save"

### Expected Result

Product is successfully createdSuccess message appearsNew product
appears in product listProduct is visible on the store page

------------------------------------------------------------------------

## C110 - Verify admin can edit an existing product

**Type:** Other

**Priority:** Medium

### Preconditions

Product already existsAdmin is logged in

### Steps

1.  Go to "Products" section2. Select an existing product3. Click
    "Edit"4. Change product details (e.g., price or title)5. Click
    "Save"

### Expected Result

Product details are updated successfullyChanges are reflected in product
listChanges are visible on the store page

------------------------------------------------------------------------

## C111 - Verify admin can view all products

**Type:** Other

**Priority:** Medium

### Preconditions

Admin is logged in

### Steps

### Expected Result

------------------------------------------------------------------------

## C112 - Verify admin can view and manage users

**Type:** Other

**Priority:** Medium

### Preconditions

Admin is logged in

### Steps

1.  Navigate to "Users" section2. View user list

### Expected Result

All registered users are displayedUser details are visible (Name, Email,
Role, Status)

------------------------------------------------------------------------

## C113 - Verify admin can change user role

**Type:** Other

**Priority:** Medium

### Preconditions

At least one user exists Admin is logged in

### Steps

1.  Go to "Users" section2. Select a user3. Change role (e.g., User →
    Admin or Admin → User)4. Save changes

### Expected Result

Role is updated successfullyChanges are reflected immediatelyUpdated
user permissions apply after role change

------------------------------------------------------------------------

## C114 - Verify product cannot be created with empty required fields

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Go to "Create Product"2. Leave required fields empty (Title, Price,
    Category, etc.)3. Click "Save"

### Expected Result

Validation errors appear for required fieldsProduct is NOT createdUser
remains on Create Product page

------------------------------------------------------------------------

## C115 - Verify system validates price field

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Enter text instead of numbers in Price field (e.g., "abc123")2.
    Enter negative value (e.g., -50)3. Click "Save"

### Expected Result

Error message appearsProduct is not createdOnly valid positive numeric
values are accepted

------------------------------------------------------------------------

## C117 - Verify system handles boundary values

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Enter extremely large price (e.g., 999999999999)2. Click "Save"

### Expected Result

Either validation prevents unrealistic valuesOr system handles large
values without crash

------------------------------------------------------------------------

## C118 - Verify admin can delete an existing product

**Type:** Other

**Priority:** Medium

### Preconditions

Product already existsAdmin is logged in

### Steps

1.  Go to "Products" section2. Select an existing product3. Click
    "delete"

### Expected Result

Product delete successfully

------------------------------------------------------------------------

## C119 - Verify product cannot be updated with invalid data

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Open existing product2. Clear title field3. Click "Save"

### Expected Result

Validation error appearsChanges are not saved

------------------------------------------------------------------------

## C120 - Verify non-admin users cannot access dashboard

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Log in as regular user2. Try to access /admin route directly

### Expected Result

Access is deniedUser is redirected (e.g., to Home or Login page)Error
message like "Access Denied" appears

------------------------------------------------------------------------

## C122 - Verify header is displayed correctly on all pages

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Open Home page2. Navigate to other pages (Products, Cart, Admin,
    etc.)

### Expected Result

Header is visible on all pagesLogo is displayed correctlyNavigation
links are aligned properlyNo overlapping elementsResponsive behavior
works on different screen sizes

------------------------------------------------------------------------

## C123 - Verify footer is displayed correctly

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Scroll to bottom of each page

### Expected Result

Footer is visible on all pagesAll links are clickableContact / copyright
information is displayed correctlyNo broken layout

------------------------------------------------------------------------

## C124 - Ensure main content loads properly

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Navigate between pages2. Observe main content section

### Expected Result

Content loads without layout shiftNo broken UI elementsNo overlapping or
hidden components

------------------------------------------------------------------------

## C125 - Verify all navigation links work

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Click each navigation link in Header2. Navigate using Footer links
    (if available)

### Expected Result

Each link redirects to correct pageURL updates correctlyNo 404 errors

------------------------------------------------------------------------

## C126 - Verify Back/Forward browser buttons

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Navigate between multiple pages2. Click browser Back button3. Click
    Forward button

### Expected Result

Pages load correctlyNo broken stateData remains consistent

------------------------------------------------------------------------

## C127 - Verify language can be changed

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Click language switcher2. Select Ukrainian (UA)3. Switch back to
    English (ENG)

### Expected Result

All UI text changes to selected languageNo mixed-language
contentButtons, labels, and messages are translated

------------------------------------------------------------------------

## C131 - Verify selected language persists

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Change language to UA2. Refresh page

### Expected Result

Selected language remains active after refresh

------------------------------------------------------------------------

## C132 - Ensure translation consistency

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Change languageNavigate through all pages

### Expected Result

Language is applied globallyNo untranslated strings

------------------------------------------------------------------------

## C133 - Ensure no JavaScript errors

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Open DevTools → ConsoleReload Home page

### Expected Result

No red errors in consoleNo uncaught exceptions

------------------------------------------------------------------------

## C134 - Ensure actions do not produce JS errors

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Add product to cart2. Remove product3. Perform search4. Switch
    language

### Expected Result

No console errors during actionsNo failed network requests
