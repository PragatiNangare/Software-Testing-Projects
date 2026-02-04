# Sweet Shop Application - Test Cases Documentation

**Project:** Sweet Shop Web Application  
**Application URL:** https://sweetshop.vivrichards.co.uk/  
**Tester:** Pragati Nangare  
**Test Period:** February 1-4, 2026  
**Total Test Cases:** 37

---

## Table of Contents

1. [Browse Sweets Page (5 Test Cases)](#browse-sweets-page)
2. [About Page (2 Test Cases)](#about-page)
3. [Login Functionality (12 Test Cases)](#login-functionality)
4. [Shopping Basket (18 Test Cases)](#shopping-basket)

---

## Browse Sweets Page

### SSWA-2: Verify Browse Sweets Page Layout

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on the home page

**Steps to Reproduce:**
1. Navigate to Sweet Shop application "https://sweetshop.vivrichards.co.uk/"
2. Observe the Browse Sweets page layout

**Expected Result:**
1. Page title 'Browse sweets' is displayed
2. Subtitle 'Browse our delicious choice of retro sweets.' is visible
3. Product cards are displayed in a grid layout
4. Each card shows product image, name, description, and price

**Test Result:** ✅ PASSED

---

### SSWA-3: Verify Navigation Menu Elements

**Priority:** High  
**Severity:** Critical  
**Type:** UI/UX  
**Automation:** Manual

**Preconditions:**
- User is on the Sweet Shop application

**Steps to Reproduce:**
1. Observe the top navigation bar
2. Verify all menu items are present

**Expected Result:**
1. Sweet Shop logo/brand is displayed on the left
2. 'Sweets' link is present
3. 'About' link is present
4. 'Login' link is present
5. 'Basket' icon with count is displayed
6. All navigation elements are clickable

**Test Result:** ✅ PASSED

---

### SSWA-4: Verify All Product Cards Displayed Correctly

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Browse Sweets page

**Steps to Reproduce:**
1. Verify all product details are displayed correctly

**Expected Result:**
1. Product image is displayed
2. Product name is shown
3. Description is displayed
4. Price visible and correctly formatted
5. "Add to Cart" button is present and clickable

**Test Result:** ❌ FAILED

**Defect:** D-3 - Wham Bar product image missing (404 error)

**Actual Result:**
- The Wham Bar product image fails to load on the Browse Sweets page due to an incorrect filename in the code
- Technical Details:
  - Incorrect filename: whan.jpg
  - Correct filename should be: wham.jpg
  - Error location: sweets:188
  - Status: 404 Not Found

---

### SSWA-5: Verify Basket Counter Display

**Priority:** Medium  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has items in basket

**Steps to Reproduce:**
1. Observe the basket icon in navigation
2. Check the item count badge

**Expected Result:**
1. Basket icon is visible in top-right navigation
2. Badge with number is displayed
3. Badge is clearly visible and properly positioned

**Test Result:** ✅ PASSED

---

### SSWA-6: Verify Product Grid Responsiveness

**Priority:** Medium  
**Severity:** Normal  
**Type:** UI/UX  
**Automation:** Manual

**Preconditions:**
- User is on Browse Sweets page

**Steps to Reproduce:**
1. View page on desktop resolution
2. Observe product card layout
3. Resize browser window
4. Observe layout changes

**Expected Result:**
1. Products display in a grid on desktop
2. All product cards are equal height
3. Images are properly scaled
4. Layout adjusts appropriately on smaller screens

**Test Result:** ❌ FAILED

**Defect:** D-4 - Product prices not aligned consistently

**Actual Result:**
- Product prices are not consistently aligned across product cards on any device size (desktop, tablet, mobile)
- Some prices appear higher or lower than others
- Creates an inconsistent and unprofessional user interface
- The CSS for price positioning is not standardized across all product cards

---

## About Page

### SSWA-7: Verify About Page Content

**Priority:** High  
**Severity:** Normal  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User can access the application

**Steps to Reproduce:**
1. Navigate to About page from main menu
2. Verify page content

**Expected Result:**
1. Page title 'Sweet Shop Project' is displayed
2. Project description paragraph is displayed
3. Text is readable and properly formatted

**Test Result:** ✅ PASSED

---

### SSWA-8: Verify Navigation to About Page

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on any page of the application

**Steps to Reproduce:**
1. Locate 'About' link in navigation menu
2. Click on 'About' link
3. Verify page redirection

**Expected Result:**
1. 'About' link is clickable
2. User is redirected to About page
3. URL changes appropriately
4. Page loads without errors

**Test Result:** ❌ FAILED

**Defect:** D-5 - About page returns 404 error

**Actual Result:**
- Clicking About link from basket page shows "Page Not Found"
- Network tab shows request for "bout" instead of "about"
- 404 error in console

---

## Login Functionality

### SSWA-9: Verify Login Page Layout

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User can access the application

**Steps to Reproduce:**
1. Navigate to Login page
2. Observe page elements

**Expected Result:**
1. Page title 'Login' is displayed
2. Instruction text is visible
3. Email address input field is present
4. Password input field is present
5. Login button is visible
6. Social media login options are displayed

**Test Result:** ✅ PASSED

---

### SSWA-10: Verify Email Input Field

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Locate email address input field
2. Verify field attributes
3. Click on field
4. Enter text

**Expected Result:**
1. Field label 'Email address' is displayed
2. Placeholder text is visible
3. Field accepts text input
4. Field is properly styled
5. Cursor appears when clicked

**Test Result:** ✅ PASSED

---

### SSWA-11: Verify Password Input Field

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Locate password input field
2. Verify field attributes (Field label 'Password' is displayed)
3. Click on field (Placeholder text 'Password' is visible)
4. Enter text

**Expected Result:**
1. Field accepts text input
2. Entered text is masked (shown as dots/asterisks)

**Test Result:** ✅ PASSED

---

### SSWA-12: Verify Login Button Appearance

**Priority:** High  
**Severity:** Major  
**Type:** UI/UX  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Locate the Login button
2. Verify button styling and text

**Expected Result:**
1. Button displays text 'Login'
2. Button has background color
3. Button appears clickable (proper cursor on hover)
4. Button is properly positioned below password field

**Test Result:** ✅ PASSED

---

### SSWA-13: Verify Social Login Options

**Priority:** Medium  
**Severity:** Normal  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Scroll below the Login button
2. Observe social media login icons

**Expected Result:**
1. Three social media icons are displayed (Twitter, Facebook, LinkedIn)
2. Icons are properly sized and colored
3. Icons are horizontally aligned
4. Icons appear clickable

**Test Result:** ❌ FAILED

**Defect:** D-6 - Social login icons non-functional

**Actual Result:**
- The social login icons (Twitter, Facebook, LinkedIn) on the Login page are displayed but completely non-functional
- When clicked, instead of redirecting to the respective social media authentication pages, the current page simply reloads
- Icons are either missing their href attributes, have broken links, or the click event handlers are not properly implemented

---

### SSWA-14: Test Login with Valid Credentials

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has valid account credentials
- User is on Login page

**Steps to Reproduce:**
1. Enter valid email in email field (Form accepts input)
2. Enter valid password in password field (Form accepts input)
3. Click Login button (Login button triggers submission)
4. Observe result

**Expected Result:**
1. User is authenticated successfully
2. User is redirected to appropriate page
3. No error messages are displayed

**Test Result:** ❌ FAILED

**Defect:** D-7 - Login accepts any credentials

**Actual Result:**
- The login functionality has no server-side validation and accepts any email and password combination
- All login attempts succeed regardless of credentials, displaying "Welcome to test.user.com" message
- This is a critical security vulnerability - the system is not verifying user credentials against a database or authentication service

---

### SSWA-15: Test Login with Empty Fields

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Leave email field empty
2. Leave password field empty
3. Click Login button
4. Observe validation

**Expected Result:**
1. Validation errors appear for both fields
2. Error messages indicate required fields
3. Form is not submitted
4. User remains on Login page

**Test Result:** ✅ PASSED

---

### SSWA-16: Test Login with Invalid Email

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Enter invalid email format (Input data: "notanemail")
2. Enter any password
3. Click Login button
4. Observe validation

**Expected Result:**
1. Validation error appears
2. Error message indicates invalid email format
3. Form is not submitted
4. User remains on Login page

**Test Result:** ❌ FAILED

**Defect:** D-8 - Email validation accepts invalid formats

**Actual Result:**
- Email field validation only checks for the presence of "@" symbol followed by any character
- Accepts improperly formatted email addresses
- Current validation accepts emails like "test@a" or "user@1" which are not valid email addresses
- Valid email format requires "@" followed by a domain name with proper structure (e.g., domain.com)

---

### SSWA-17: Test Login with Wrong Password

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has a valid email but enters wrong password

**Steps to Reproduce:**
1. Enter valid email address
2. Enter incorrect password
3. Click Login button
4. Observe result

**Expected Result:**
1. Error message displays 'Invalid credentials' or similar
2. User remains on Login page
3. Password field may be cleared for security

**Test Result:** ❌ FAILED

**Defect:** D-9 - Password field accepts any input

**Actual Result:**
- The password field has no validation whatsoever
- Any password is accepted for any email address, confirming there is no authentication mechanism in place
- This demonstrates a complete absence of login security
- The system should validate passwords against stored credentials and reject incorrect passwords

---

### SSWA-18: Test Password Field Masking

**Priority:** Medium  
**Severity:** Normal  
**Type:** Security  
**Automation:** Manual

**Preconditions:**
- User is on login page

**Steps to Reproduce:**
1. Click on password field
2. Type any password (Input data: "TestPassword123")
3. Observe displayed characters

**Expected Result:**
1. Typed characters are masked as dots or asterisks
2. Actual password text is not visible
3. Character count matches typed length

**Test Result:** ✅ PASSED

---

### SSWA-19: Verify Required Field Indicators

**Priority:** Medium  
**Severity:** Minor  
**Type:** Functional 
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Observe email and password field labels
2. Check for required field indicators

**Expected Result:**
- Required field indicators (asterisk or other marking) are displayed if applicable, or HTML5 'required' attribute is present

**Test Result:** ✅ PASSED

---

### SSWA-20: Test Tab Navigation Between Fields

**Priority:** Low  
**Severity:** Normal  
**Type:** Accessibility  
**Automation:** Manual

**Preconditions:**
- User is on Login page

**Steps to Reproduce:**
1. Click on email field
2. Press Tab key
3. Observe focus movement
4. Press Tab key again

**Expected Result:**
1. Focus moves from email to password field
2. Focus moves from password to Login button
3. Tab order is logical and sequential

**Test Result:** ✅ PASSED

---

## Shopping Basket

### SSWA-21: Verify Basket Page Layout

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has items in basket

**Steps to Reproduce:**
1. Navigate to Basket page
2. Observe page layout and sections

**Expected Result:**
1. Page title 'Your Basket' is displayed
2. Instruction text is visible
3. Billing address section is present
4. Payment section is present
5. Basket summary is displayed
6. Delivery options are shown

**Test Result:** ✅ PASSED

---

### SSWA-22: Verify Basket Items Display

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has items in basket

**Steps to Reproduce:**
1. Navigate to Basket page
2. Locate 'Your Basket' section
3. Review item details

**Expected Result:**
1. Badge shows count of items
2. Item details and price is displayed
3. Each item has a 'Delete Item' link
4. Items are clearly separated

**Test Result:** ✅ PASSED

---

### SSWA-23: Verify Basket Total Calculation

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has items in basket

**Steps to Reproduce:**
1. Navigate to Basket page
2. Review item prices
3. Check total amount

**Expected Result:**
1. Individual item prices are displayed correctly
2. Total calculation is accurate
3. Currency symbol is properly formatted

**Test Result:** ❌ FAILED

**Defect:** D-10 - Basket total incorrect for duplicate items

**Actual Result:**
- When the same product is added to the basket multiple times, the total calculation only includes the price of one item instead of multiplying by quantity
- For example, adding 2x items at £1.00 each should show £2.00, but the system only shows £1.00
- The basket is not properly calculating (price × quantity) for duplicate items

---

### SSWA-24: Verify Delete Item Functionality

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- Basket contains at least one item

**Steps to Reproduce:**
1. Navigate to Basket page
2. Locate 'Delete Item' link under any item
3. Click 'Delete Item'
4. Observe changes

**Expected Result:**
1. Item is removed from basket
2. Basket counter updates (decrements by 1)
3. Total amount recalculates
4. Basket summary refreshes
5. Confirmation or update occurs

**Test Result:** ✅ PASSED

---

### SSWA-25: Verify Empty Basket Functionality

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- Basket contains items

**Steps to Reproduce:**
1. Navigate to Basket page
2. Locate 'Empty Basket' link
3. Click 'Empty Basket'
4. Observe result

**Expected Result:**
1. All items are removed from basket
2. Basket counter shows '0'
3. Total shows '£0.00' or appropriate empty state
4. Confirmation message may appear
5. Basket summary updates appropriately

**Test Result:** ✅ PASSED

---

### SSWA-26: Verify Billing Address Section

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on basket page

**Steps to Reproduce:**
1. Locate 'Billing address' section
2. Review all form fields

**Expected Result:**
1. Section header 'Billing address' is displayed
2. First name field is present
3. Last name field is present
4. Email field with placeholder is present
5. Address field with placeholder is present
6. Address 2 field (Optional) with placeholder is present
7. All fields are properly labeled

**Test Result:** ✅ PASSED

---

### SSWA-27: Verify Billing Address Dropdowns

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on basket page

**Steps to Reproduce:**
1. Locate Country dropdown
2. Locate City dropdown
3. Click on each dropdown (Country dropdown displays 'Choose...', City dropdown displays 'Choose...')
4. Verify options

**Expected Result:**
- Dropdowns are functional and show options when clicked

**Test Result:** ✅ PASSED

---

### SSWA-28: Verify Payment Section

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on basket page

**Steps to Reproduce:**
1. Scroll to Payment section
2. Review all payment fields

**Expected Result:**
1. Section header 'Payment' is displayed
2. 'Name on card' field is present with helper text
3. 'Credit card number' field is present
4. 'Expiration' field is present
5. 'CVV' field is present
6. All fields are properly aligned and labeled

**Test Result:** ✅ PASSED

---

### SSWA-29: Verify Delivery Options

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on basket page

**Steps to Reproduce:**
1. Locate Delivery section in basket summary
2. Review delivery options

**Expected Result:**
1. Section header 'Delivery' is displayed
2. 'Collect (FREE)' option is available with radio button
3. 'Standard Shipping (£1.99)' option is available with radio button
4. One option is pre-selected (likely Collect)
5. Selecting different option updates total

**Test Result:** ✅ PASSED

---

### SSWA-30: Verify Promo Code Section

**Priority:** Medium  
**Severity:** Normal  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on basket page

**Steps to Reproduce:**
1. Locate promo code section
2. Review elements

**Expected Result:**
1. 'Promo code' input field is present
2. 'Redeem' button is displayed next to input
3. Field accepts text input
4. Button is clickable

**Test Result:** ✅ PASSED

---

### SSWA-31: Test Promo Code Application

**Priority:** Medium  
**Severity:** Normal  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User has a valid promo code
- User is on Basket page with items

**Steps to Reproduce:**
1. Enter valid promo code in field
2. Click 'Redeem' button
3. Observe result

**Expected Result:**
1. System validates promo code
2. If valid, discount is applied to total
3. Confirmation message appears
4. Total amount is recalculated
5. Discount is shown in summary

**Test Result:** ❌ FAILED

**Defect:** D-11 - Promo code field non-functional

**Actual Result:**
- The promo code redemption feature is completely non-functional
- No promo codes are provided anywhere in the application
- When any test code is entered and "Redeem" clicked, nothing happens - no error message, no success message, no total change
- There is no user feedback at all, suggesting the backend validation or the button event handler is not implemented

---

### SSWA-32: Verify Continue to Checkout Button

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Basket page with items

**Steps to Reproduce:**
1. Scroll to bottom of page
2. Locate 'Continue to checkout' button
3. Verify button properties

**Expected Result:**
1. Button is prominently displayed
2. Button text 'Continue to checkout' is clearly visible
3. Button appears clickable

**Test Result:** ❌ FAILED

**Defect:** D-12 - Checkout button doesn't navigate

**Actual Result:**
- The "Continue to checkout" button is clickable but does not navigate to a checkout confirmation or payment processing page as expected
- Instead, it simply reloads the current basket page
- This prevents users from completing their purchase
- The form has no action attribute

---

### SSWA-33: Test Checkout with Empty Required Fields

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Basket page

**Steps to Reproduce:**
1. Leave all billing fields empty
2. Leave all payment fields empty
3. Click 'Continue to checkout' button
4. Observe validation

**Expected Result:**
1. Form validation triggers
2. Error messages appear for required fields
3. User cannot proceed to checkout
4. First invalid field receives focus
5. Clear error indicators are displayed

**Test Result:** ✅ PASSED

---

### SSWA-34: Test Total Recalculation on Delivery Change

**Priority:** High  
**Severity:** Critical  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Basket page with items

**Steps to Reproduce:**
1. Note current total with 'Collect (FREE)' selected
2. Select 'Standard Shipping (£1.99)'
3. Observe total (Selecting Standard Shipping adds £1.99 to total, New total = Original total + £1.99)
4. Switch back to 'Collect (FREE)'
5. Observe total again

**Expected Result:**
1. Selecting Collect removes shipping charge
2. Total returns to original amount
3. All calculations are accurate

**Test Result:** ❌ FAILED

**Defect:** D-13 - Total shows NaN on delivery change

**Actual Result:**
- Selecting the Standard Shipping (£1.99) option triggers a recalculation of the basket total
- Although the shipping value itself is numeric, the calculation fails due to improper handling of numeric data within the getCartDetails() function
- One or more values used in the calculation (such as the basket subtotal) are treated as strings or undefined, causing the arithmetic operation to return NaN
- No JavaScript error is thrown in the console, as NaN is produced silently

---

### SSWA-35: Verify Credit Card Number Field Validation

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Basket page

**Steps to Reproduce:**
1. Click on credit card number field
2. Enter invalid card number (Input data: "1234")
3. Tab out of field
4. Observe validation

**Expected Result:**
1. Field accepts numeric input
2. Validation error appears for invalid card number
3. Error message is clear and specific

**Test Result:** ❌ FAILED

**Defect:** D-14 - Credit card field accepts invalid input

**Actual Result:**
- The credit card field allows typing letters, symbols, and numbers of any length up to 19 digits
- However, the form does not submit because HTML5 validation (required and maxlength) prevents submission
- No numeric-only or Luhn algorithm validation is implemented
- This may confuse users and could allow invalid input if server-side checks are not in place

---

### SSWA-36: Test CVV Field Input Restrictions

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Basket page

**Steps to Reproduce:**
1. Click on CVV field
2. Try entering letters
3. Try entering more than 3 digits
4. Enter valid 3-digit CVV

**Expected Result:**
1. Field only accepts numeric input
2. Field limits input to 3-4 characters
3. Non-numeric characters are rejected or filtered
4. Valid CVV is accepted

**Test Result:** ❌ FAILED

**Defect:** D-15 - CVV field has number spinner

**Actual Result:**
- The CVV field is implemented as type="number", which displays up/down spinners
- Users can click the down arrow or manually type negative numbers, which is invalid for CVV
- There is no restriction on input length or numeric range, allowing CVVs of 1-5 digits or negative values
- Proper validation should enforce 3-4 positive digits only, either using type="text" with a regex pattern or type="number" with min/max constraints

---

### SSWA-37: Verify Email Field Validation in Billing

**Priority:** High  
**Severity:** Major  
**Type:** Functional  
**Automation:** Manual

**Preconditions:**
- User is on Basket page

**Steps to Reproduce:**
1. Enter invalid email format in Email field
2. Tab out or submit form
3. Observe validation

**Expected Result:**
1. Validation error appears
2. Error message indicates invalid email format

**Test Result:** ❌ FAILED

**Defect:** D-16 - Billing email accepts invalid format

**Actual Result:**
- The billing email field uses type="email", which enforces basic HTML5 validation
- Inputs like "test@" are rejected (checkValidity() returns false)
- However, the field does not enforce a proper domain or top-level domain (TLD), so inputs like "user@x" are still accepted
- This weak validation could allow technically invalid email addresses, potentially causing issues with order confirmations and customer communication

---

## Test Execution Timeline

| Date | Test Suite | Test Cases | Passed | Failed |
|------|------------|------------|--------|--------|
| 2026-02-01 | Browse Sweets Page | 5 | 3 | 2 |
| 2026-02-03 | About Page | 2 | 1 | 1 |
| 2026-02-04 | Login Functionality | 12 | 8 | 4 |
| 2026-02-04 | Shopping Basket | 18 | 10 | 7 |

---

## Summary

**Total Test Cases:** 37  
**Passed:** 22 (59.5%)  
**Failed:** 15 (40.5%)  
**Defects Found:** 16

---

**Last Updated:** February 4, 2026  
**Document Version:** 1.0
