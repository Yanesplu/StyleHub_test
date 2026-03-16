# StyleHub Test Cases

------------------------------------------------------------------------

## C38 - Verify successful user registration with valid data

**Type:** Functional

**Priority:** High

### Preconditions
Open site:
https://qatestingapp.netlify.app/

User is on Registration page

### Steps

1.  Enter valid name
2. Enter valid email
3.  Enter valid password
4.   Select  role "user"
5. Submit form
Verify record in database using SQL query

Test Data: a@mail.com

### Expected Result

User account is successfully created and system redirects user to Login page.
User record created in DB

------------------------------------------------------------------------

## C39 - Verify mock email verification redirects to login

**Type:** Functional

**Priority:** Medium

### Preconditions

User completed registration

### Steps

1.  Enter any verification code
2.  Submit

### Expected Result

Account is verified and user is redirected to Login page.

------------------------------------------------------------------------

## C40 - Verify registration fails with empty required fields

**Type:** Functional

**Priority:** High

### Preconditions

Registration page opened

### Steps

1.  Leave fields empty
2.   Click Submit

### Expected Result

Validation errors are displayed.

------------------------------------------------------------------------

## C41 - Verify registration fails with invalid email format

**Type:** Negative

**Priority:** High

### Preconditions

Registration page opened

### Steps

1.  Enter invalid email (example@)
2.   Fill other fields correctly
3.   Submit

### Expected Result

Error message about invalid email format is displayed.

------------------------------------------------------------------------

## C42 - Verify registration fails with already existing email

**Type:** Negative

**Priority:** High

### Preconditions

User with email already exists in DB

### Steps

1.  Enter existing email
2.   Fill other fields3. Submit

### Expected Result

System displays "Email already exists" error.

------------------------------------------------------------------------

## C43 - Verify successful login with valid credentials

**Type:** Functional

**Priority:** Critical

### Preconditions

User is registered

### Steps

1.  Enter correct email
2.   Enter correct password
    3.  Click Login

### Expected Result

User is logged in and redirected to Home page.

------------------------------------------------------------------------

## C44 - Verify login fails with incorrect password

**Type:** Negative

**Priority:** Medium

### Preconditions

User exists

### Steps

1.  Enter correct email
2.   Enter wrong password
    3.  Click Login

### Expected Result

Error message is displayed.

------------------------------------------------------------------------

## C45 - Verify login fails with non-existing email

**Type:** Negative

**Priority:** High

### Preconditions

Login page opened

### Steps

1. Enter unregistered email
2. Enter password
3. Click Login

### Expected Result

Error message is displayed.

------------------------------------------------------------------------

## C46 - Verify SQL injection attempt in login field

**Type:** Security

**Priority:** Critical

### Preconditions

Login page opened

### Steps

1.  Enter ' OR 1=1 -- in email field
2.   Enter random password
3.  Click  login

### Expected Result

Login fails and system does not authenticate user.

------------------------------------------------------------------------

## C47 - Verify logout functionality

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged in

### Steps

Click Sign Out

### Expected Result

User is logged out and redirected to Home page.

------------------------------------------------------------------------

## C57 - Verify favourites list updates after removing product

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged inAt least 1 product in favourites

### Steps

1.  Open Favourites section
2.  Remove one product from favourites
3.  Refresh page

### Expected Result

Removed product is no longer displayed

------------------------------------------------------------------------

## C48 - Verify authorized user can access Profile page

**Type:** Functional

**Priority:** Medium

### Preconditions

Test Data:
Email: 
testuser@example.com
Password: ValidPass1231. 
User account exists in database
User is logged in

### Steps

1.  Login with valid credentials
2. Click on "Profile" link in header

### Expected Result

1.  User is redirected to /profile page. User information is displayed

------------------------------------------------------------------------

## C49 - Verify unauthorized user cannot access Profile page

**Type:** Functional

**Priority:** Medium

### Preconditions

User is logged out

### Steps

1.  Manually enter /profile URL in browser
2.  Press Enter

### Expected Result

System redirects user to Login page  
Profile data is not displayed

------------------------------------------------------------------------

## C50 - Verify user can successfully update Name

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged inNew Name: Noname

### Steps

1.  Open Profile page
2.Change Name field
3. Click Save
4. Refresh page

### Expected Result

1. Success response is returned from API
2. Name is updated in UI
3. Database contains updated Name value

------------------------------------------------------------------------

## C52 - Verify user cannot save empty name

**Type:** Functional

**Priority:** Medium

### Preconditions

Profile page opened

### Steps

1.  Clear Name field
2. Click Save

### Expected Result

Validation error is displayed and data is not updated.

------------------------------------------------------------------------

## C53 - Verify user can change password successfully

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged incurrent password: 12345new: 123456

### Steps

1.  Enter correct current password
2. Enter new password
3. Confirm new password
4. Click Save
5. Logout
6. Login with new password

### Expected Result

Password update request returns success status  
Old password no longer works

------------------------------------------------------------------------

## C54 - Verify password change fails with incorrect current password

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged in

### Steps

1.  Enter incorrect current password
2. Enter new password
3. Click Save

### Expected Result

System displays error message  
Password is not changed

------------------------------------------------------------------------

## C55 - Verify user can view favourite

**Type:** Functional

**Priority:** Medium

### Preconditions

1.  User account exists
2. User logged in
3. At least 1 product added tofavourites

### Steps

1.  Open home page
2. Click to product
3. Add to favorite
4. Click to User page
5. Open "Favourites" section

### Expected Result

List of favourite products is displayed

------------------------------------------------------------------------

## C56 - Verify empty favourites state is handled correctly

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged inUser has no favourite products

### Steps

1.  Navigate to Profile page
2.  Open "Favourites" section

### Expected Result

System displays message like: "No favourite products yet"  
No errors appear in console

------------------------------------------------------------------------

## C58 - Verify user can view order history

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged inAt least one completed order exists in database

### Steps

1. Login
2. Navigate to Profile page
3. Open "Orders" section

### Expected Result

List of previous orders is displayed  
Each order contains:  
-Order ID  
-Date  
-Total amount  
-List of purchased products  

------------------------------------------------------------------------

## C59 - Verify empty order history is handled correctly

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged inNo orders in database

### Steps

1.  Navigate to Profile page
2.  Open Orders section

### Expected Result

Message displayed: "No orders yet"

------------------------------------------------------------------------

## C60 - Verify product page loads correctly

**Type:** Functional

**Priority:** High

### Preconditions

Product exists in database

### Steps

1.  Navigate to Home page2. Click on any product

### Expected Result

Product page opens successfully  
Correct product information is displayed  
Network request returns 200  

------------------------------------------------------------------------

## C61 - Verify product details match database records

**Type:** Other

**Priority:** Medium

### Preconditions

Product exists in DB

### Steps

1.  Open Product page
2.  Compare displayed data with database values

### Expected Result

Title matches DB  
Description matches DB  
Price matches DB  
Available quantity matches DB  

------------------------------------------------------------------------

## C62 - Verify user can add product to cart

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged inProduct in stock

### Steps

1.  Open Product page
2.  Click "Add to Cart"

### Expected Result

Product added to cart  
Cart counter updates  
API returns success  
Productappears in Cart page  

------------------------------------------------------------------------

## C63 - Verify user cannot add out-of-stock product to cart

**Type:** Functional

**Priority:** Medium

### Preconditions

Product quantity = 0

### Steps

1.  Open Product page
2.  Click "Add to Cart"

### Expected Result

Add action blocked  
Proper message displayed  
No incorrect order created  

------------------------------------------------------------------------

## C65 - Verify user can add product to favourites

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged in

### Steps

1. Open Product page
2. Click "Add to Favourites"
3. Click to Profile page
4. Click "Favourites"

### Expected Result

Product added to favourites  
Icon changes state  
Product appears in Profile → Favourites  

------------------------------------------------------------------------

## C66 - Verify duplicate product is not added multiple times to favourites

**Type:** Functional

**Priority:** Medium

### Preconditions

Product already in favourites

### Steps

Click "Add to Favourites" again

### Expected Result

Product not duplicated  
No duplicate entry in DB  

------------------------------------------------------------------------

## C68 - Verify product reviews are displayed

**Type:** Functional

**Priority:** Medium

### Preconditions

Product has reviews in DB

### Steps

1.  Open Product page
2. Scroll to Reviews section

### Expected Result

All reviews are displayedEach review shows:  
-User name  
-Rating  
-Comment  

------------------------------------------------------------------------

## C69 - Verify user can add review to product

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged in

### Steps

1. Open Product page
2. Enter review text
3. Select rating
4. Submit review

### Expected Result

Review successfully saved  
Review appears in list after refresh  
API returns 201  
DB contains new review record  

------------------------------------------------------------------------

## C70 - Verify unauthorized user cannot add review

**Type:** Functional

**Priority:** Medium

### Preconditions

User logged out

### Steps

1.  Open Product page
2.  Attempt to submit review

### Expected Result

User redirected to Login OR Login to wtire a review  
Review not saved in DB  

------------------------------------------------------------------------

## C71 - Verify invalid product ID returns error page

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

Manually enter invalid product ID in URL

### Expected Result

Product not found  
API returns 404  
No application crashNo sensitive data exposed  

------------------------------------------------------------------------

## C72 - Verify carousel visibility

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on Home Page

### Steps

1.  Open Home Page
2.  Observe the hero carousel at the top of the page

### Expected Result

Carousel is visible and properly displayed

------------------------------------------------------------------------

## C73 - Verify carousel navigation (next/previous)

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Click the "Next" arrow on the carousel
2. Click the "Previous" arrow

### Expected Result

Carousel slides to the next and previous images correctly

------------------------------------------------------------------------

## C74 - Verify carousel auto-slide

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

Wait for the carousel to auto-slide

### Expected Result

Carousel automatically transitions to the next image after the set
interval

------------------------------------------------------------------------

## C75 - Verify carousel click action

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

Click on a carousel image

### Expected Result

User is redirected to the correct page or link associated with the
carousel image

------------------------------------------------------------------------

## C77 - Verify products are displayed

**Type:** Functional

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

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

### Expected Result

------------------------------------------------------------------------


## C82 - Verify page navigation

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Click a page number
2. Click "Next" button
3. Click "Previous" button

### Expected Result

Product grid updates according to the selected page

------------------------------------------------------------------------

## C87 - Search by Title

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on the category or home page

### Steps

1.  Enter full product title in search bar (e.g., "Blue Cotton
    T-Shirt")
 2. Click Search / press Enter

### Expected Result

Only product(s) with exact title are displayed  
No unrelated products are shown  

------------------------------------------------------------------------

## C88 - Verify search handles no matching results correctly

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on the category or home page

### Steps

1.  Enter a non-existing product name (Red Unicorn Jacket)
2.  Click Search / press Enter

### Expected Result

No products are displayed  
A message like "No products found" appears  
Page layout remains correct  

------------------------------------------------------------------------

## C89 - Verify search returns products that partially match input

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on the category or home page

### Steps

1.  Enter a partial product title (e.g., "Cotton")
2. Click Search /press Enter

### Expected Result

All products containing the input text in their title are displayed  
Products without the partial word are not displayed  

------------------------------------------------------------------------

## C90 - Verify user can add a product to the cart

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on a product page or product grid; product is in stock

### Steps

1.  Click "Add to Cart" on a product
2.  Open "Cart"

### Expected Result

Product is added to the cart  
Cart count updates correctly  
Product details (name, price, quantity) are correct in the cart  

------------------------------------------------------------------------

## C91 - Verify user can remove a product from the cart

**Type:** Functional

**Priority:** Medium

### Preconditions

Cart has at least one product

### Steps

1.  Open the cart
2.  Click "Remove" on a product

### Expected Result

Product is removed from the cart  
Cart count updates correctly  
Cart total updates correctly  

------------------------------------------------------------------------

## C92 - Verify cart total calculation is correct

**Type:** Functional

**Priority:** Medium

### Preconditions

Cart has one or more products

### Steps

1. Add multiple products to the cart with known prices
2. Observe the total price displayed in the cart
3. Change quantity of one product and observe the updated total
4. Remove a product and check the updated total

### Expected Result

Total price equals the sum of all product prices × quantities  
Updates correctly when quantities change or products are removed  
No rounding or calculation errors  

------------------------------------------------------------------------

## C94 - Verify Items in Cart Increment Instead of Duplicate

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on the product page or product grid.
Cart may be empty or have other products.
Product is in stock.

### Steps

1. Click "Add to Cart" on a specific product (e.g., "Blue T-Shirt").
2. Open the cart and note the quantity of that product.
3. Click "Add to Cart" again for the same product.
4. Repeat for a few more times if needed

### Expected Result

The cart shows only one entry for that product. 
The quantity increments with each addition  
No duplicate product rows appear in the cart.  

------------------------------------------------------------------------

## C96 - Verify empty cart cannot Proceed to Payment

**Type:** Functional

**Priority:** Medium

### Preconditions

User is on the website.Cart is empty.

### Steps

1. Open the cart page.
2. Verify that the cart has no products.
3.Attempt to click "Proceed to Payment" or "Checkout".

### Expected Result

The "Proceed to Payment" button should be disabled or unclickable. 
If clicked, a message should appear: "Your cart is empty" or similar. 
User cannot access payment page until at least one product is added.  

------------------------------------------------------------------------

## C101 - Verify mock payment flow works correctly

**Type:** Functional

**Priority:** Medium

### Preconditions

User has at least one product in cartUser is on Checkout/Payment page

### Steps

1. Proceed to Payment page
2. Enter valid mock payment details
3. Click "Pay Now"

### Expected Result

Payment request is processedUser is redirected to confirmation/success page  
Order is created successfully  

------------------------------------------------------------------------

## C102 - Verify successful payment scenario

**Type:** Functional

**Priority:** Medium

### Preconditions

Cart contains productsUser is on Payment page

### Steps

1.  Enter valid card details
2.  Confirm payment
3.  Wait for response

### Expected Result

Payment is successfulSuccess message appears  
Order confirmation page is displayed  
Cart is clearedOrder ID is generated  

------------------------------------------------------------------------

## C103 - Verify system handles failed payment properly

**Type:** Functional

**Priority:** Medium

### Preconditions

Enter invalid or declined card detailsClick "Pay Now"

### Steps

1.  Enter invalid or declined card details
2.  Click "Pay Now"

### Expected Result

Payment is declinedError message appears (e.g., "Payment Failed" or "Card Declined")  
User remains on payment page  
Cart is NOT cleared  
User can retry payment  

------------------------------------------------------------------------

## C104 - Verify required field validation

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Leave required fields empty
2.  Click "Pay Now"

### Expected Result

Validation errors appear  
Payment is not processed  

------------------------------------------------------------------------

## C106 - Verify card number format validation

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Enter invalid card number (e.g., letters or too short number)
2.  Click "Pay Now"

### Expected Result

Validation error appears  
Payment is not processed  

------------------------------------------------------------------------

## C107 - Verify expired card cannot be used

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Enter expired expiration date
2.  Click "Pay Now"

### Expected Result

Error message appears  
Payment is blocked  

------------------------------------------------------------------------

## C108 - Verify system stability during refresh

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Start payment process
2. Refresh page

### Expected Result

No duplicate charge occurs  
System handles session correctly  

------------------------------------------------------------------------

## C109 - Verify admin can create a new product

**Type:** Functional

**Priority:** Medium

### Preconditions

Admin is logged in
Admin is on Dashboard page

### Steps

1.  Navigate to "Products" section
2.  Click "Create Product" / "Add Product"
3. Fill in all required fields (Title, Price, Category, Description, Image, Stock)
4. Click "Save"

### Expected Result

Product is successfully created  
Success message appears  
New product appears in product list  
Product is visible on the store page  

------------------------------------------------------------------------

## C110 - Verify admin can edit an existing product

**Type:** Functional

**Priority:** Medium

### Preconditions

Product already existsAdmin is logged in

### Steps

1. Go to "Products" section
2. Select an existing product
3. Click "Edit"
4. Change product details (e.g., price or title)
5. Click "Save"

### Expected Result

Product details are updated successfully  
Changes are reflected in product list  
Changes are visible on the store page  

------------------------------------------------------------------------

## C111 - Verify admin can view all products

**Type:** Functional

**Priority:** Medium

### Preconditions

Admin is logged in

### Steps

### Expected Result

------------------------------------------------------------------------

## C112 - Verify admin can view and manage users

**Type:** Functional

**Priority:** Medium

### Preconditions

Admin is logged in

### Steps

1.  Navigate to "Users" section
2.  View user list

### Expected Result

All registered users are displayed  
User details are visible (Name, Email, Role, Status)  

------------------------------------------------------------------------

## C113 - Verify admin can change user role

**Type:** Functional

**Priority:** Medium

### Preconditions

At least one user exists Admin is logged in

### Steps

1. Go to "Users" section
2. Select a user
3. Change role (e.g., User → Admin or Admin → User)
4. Save changes

### Expected Result

Role is updated successfully  
Changes are reflected immediately  
Updated user permissions apply after role change  

------------------------------------------------------------------------

## C114 - Verify product cannot be created with empty required fields

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1. Go to "Create Product"
2. Leave required fields empty (Title, Price, Category, etc.)
3. Click "Save"

### Expected Result

Validation errors appear for required fields  
Product is NOT created  
User remains on Create Product page  

------------------------------------------------------------------------

## C115 - Verify system validates price field

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Enter text instead of numbers in Price field (e.g., "abc123")
2.  Enter negative value (e.g., -50)
3.  Click "Save"

### Expected Result

Error message appears  
Product is not created  
Only valid positive numeric values are accepted  

------------------------------------------------------------------------

## C117 - Verify system handles boundary values

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Enter extremely large price (e.g., 999999999999)
2.  Click "Save"

### Expected Result

Either validation prevents unrealistic values 
Or system handles large values without crash

------------------------------------------------------------------------

## C118 - Verify admin can delete an existing product

**Type:** Functional

**Priority:** Medium

### Preconditions

Product already exists
Admin is logged in

### Steps

1. Go to "Products" section
2. Select an existing product
3. Click "delete"

### Expected Result

Product delete successfully

------------------------------------------------------------------------

## C119 - Verify product cannot be updated with invalid data

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1. Open existing product
2. Clear title field
3. Click "Save"

### Expected Result

Validation error appears  
Changes are not saved  

------------------------------------------------------------------------

## C120 - Verify non-admin users cannot access dashboard

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Log in as regular user
2. Try to access /admin route directly

### Expected Result

Access is deniedUser is redirected (e.g., to Home or Login page)  
Error message like "Access Denied" appears  

------------------------------------------------------------------------

## C122 - Verify header is displayed correctly on all pages

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Open Home page
2.  Navigate to other pages (Products, Cart, Admin, etc.)

### Expected Result

Header is visible on all pages  
Logo is displayed correctly  
Navigation links are aligned properly  
No overlapping elements  
Responsive behavior works on different screen sizes  

------------------------------------------------------------------------

## C123 - Verify footer is displayed correctly

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

Scroll to bottom of each page

### Expected Result

Footer is visible on all pages  
All links are clickable  
Contact / copyright information is displayed correctly  
No broken layout  

------------------------------------------------------------------------

## C124 - Ensure main content loads properly

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Navigate between pages
2.  Observe main content section

### Expected Result

Content loads without layout shift  
No broken UI elements  
No overlapping or hidden components  

------------------------------------------------------------------------

## C125 - Verify all navigation links work

**Type:** Functional

**Priority:** Medium

### Preconditions

### Steps

1.  Click each navigation link in Header
2.  Navigate using Footer links

### Expected Result

Each link redirects to correct page  
URL updates correctly  
No 404 errors  

------------------------------------------------------------------------

## C126 - Verify Back/Forward browser buttons

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Navigate between multiple pages
2.  Click browser Back button
3.  Click Forward button

### Expected Result

Pages load correctly  
No broken state  
Data remains consistent  

------------------------------------------------------------------------

## C127 - Verify language can be changed

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Click language switcher
2.  Select Ukrainian (UA)
3.  Switch back to English (ENG)

### Expected Result

All UI text changes to selected language  
No mixed-language contentButtons, labels, and messages are translated  

------------------------------------------------------------------------

## C131 - Verify selected language persists

**Type:** Other

**Priority:** Medium

### Preconditions

### Steps

1.  Change language to UA
2.  Refresh page

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

1. Add product to cart
2. Remove product
3. Perform search
4. Switch language

### Expected Result

No console errors during actions  
No failed network requests  
