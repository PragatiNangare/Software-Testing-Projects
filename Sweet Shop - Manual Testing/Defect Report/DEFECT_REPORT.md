# Sweet Shop Application - Defect Report

**Project:** Sweet Shop Web Application  
**Application URL:** https://sweetshop.vivrichards.co.uk/  
**Tester:** Pragati Nangare  
**Test Period:** 1st Feb - 4th Feb, 2026  
**Total Defects:** 16

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Critical Defects (5)](#critical-defects)
3. [High Severity Defects (4)](#high-severity-defects)
4. [Medium Severity Defects (7)](#medium-severity-defects)
5. [Defect Statistics](#defect-statistics)

---

## Executive Summary

### Defect Distribution

| Severity | Count | Percentage |
|----------|-------|------------|
| Critical | 5 | 31.25% |
| High | 4 | 25.00% |
| Medium | 7 | 43.75% |
| **Total** | **16** | **100%** |

### Module-wise Defect Distribution

| Module | Defects | Critical | High | Medium |
|--------|---------|----------|------|--------|
| Browse Sweets Page | 2 | 0 | 1 | 1 |
| About Page | 1 | 0 | 1 | 0 |
| Login Functionality | 4 | 2 | 2 | 0 |
| Shopping Basket | 9 | 3 | 0 | 6 |
| **Total** | **16** | **5** | **4** | **7** |

### Priority Distribution

| Priority | Count |
|----------|-------|
| P1 (Urgent) | 5 |
| P2 (High) | 4 |
| P3 (Medium) | 7 |

---

## Critical Defects

### D-7: Login Accepts Any Credentials - No Authentication

**Defect ID:** D-7  
**Test Case:** SSWA-14 - Test Login with Valid Credentials  
**Reported Date:** 2026-02-04  
**Severity:** Critical  
**Priority:** P1  
**Status:** Open  
**Module:** Login Functionality

**Summary:**  
The login functionality has complete absence of authentication validation, allowing any email and password combination to successfully log in.

**Description:**  
The login system has no server-side validation and accepts any email and password combination. All login attempts succeed regardless of credentials, displaying "Welcome to test.user.com" message. This is a critical security vulnerability as there is no actual authentication occurring - the system is not verifying user credentials against a database or authentication service.

**Steps to Reproduce:**
1. Navigate to Login page (https://sweetshop.vivrichards.co.uk/login.html)
2. Enter any email (e.g., "random@email.com")
3. Enter any password (e.g., "12345" or "wrongpass")
4. Click Login button

**Expected Result:**
- System should validate credentials against stored user data
- Invalid credentials should be rejected with error message
- Only valid username/password combinations should grant access
- Error message: "Invalid credentials" or similar

**Actual Result:**
- System accepts ALL email/password combinations
- All login attempts succeed
- Displays success message: "Welcome to test.user.com"
- No authentication validation is performed
- No error messages for incorrect credentials
- Anyone can access the system without valid accounts

**Evidence:**
- Screen recording showing successful login with random credentials
- Console shows no authentication API calls

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10
- URL: https://sweetshop.vivrichards.co.uk/login.html

**Impact:**
- **Business Impact:** Complete security breach - any user can access the system
- **Data Security:** All user data and system features are accessible without authentication
- **User Trust:** Severe violation of user security expectations
- **Compliance:** Violation of basic security standards

**Root Cause:**
- No backend authentication mechanism implemented
- Missing credential validation logic
- No database lookup for user verification

**Recommendation:**
1. Implement server-side authentication mechanism
2. Validate credentials against secure user database
3. Implement password hashing and salting
4. Add rate limiting to prevent brute force attacks
5. Implement session management
6. Add CAPTCHA for multiple failed attempts

---

### D-9: Password Field Accepts Any Input - No Validation

**Defect ID:** D-9  
**Test Case:** SSWA-17 - Test Login with Wrong Password  
**Reported Date:** 2026-02-04  
**Severity:** Critical  
**Priority:** P1  
**Status:** Open  
**Module:** Login Functionality

**Summary:**  
Password field has no validation and accepts any password for any email address, confirming complete absence of authentication security.

**Description:**  
The password field has no validation whatsoever. Any password is accepted for any email address, further confirming there is no authentication mechanism in place. This demonstrates a complete absence of login security. The system should validate passwords against stored credentials and reject incorrect passwords.

**Steps to Reproduce:**
1. Navigate to Login page
2. Enter any email address (e.g., "user@example.com")
3. Enter any random password (e.g., "wrong", "123", "abc")
4. Click Login button

**Expected Result:**
- System should validate password against stored credentials
- Incorrect passwords should be rejected
- Error message: "Invalid credentials" or "Incorrect password"
- User remains on Login page
- Password field may be cleared for security

**Actual Result:**
- System accepts ALL passwords regardless of correctness
- No password validation or verification occurs
- Login succeeds with any password input
- No error message for incorrect passwords
- Authentication completely bypassed

**Evidence:**
- Test results showing successful login with multiple incorrect passwords
- No validation errors in console

**Environment:**
- Browser: Chrome 
- OS: Windows 11

**Impact:**
- **Security:** Complete bypass of password-based authentication
- **User Accounts:** All user accounts are vulnerable to unauthorized access
- **Data Privacy:** Personal information accessible without proper credentials

**Root Cause:**
- No password verification logic
- Missing backend authentication service
- No password comparison against stored credentials

**Recommendation:**
1. Implement password verification against secure database
2. Hash passwords using bcrypt or similar
3. Compare hashed passwords securely
4. Implement account lockout after failed attempts
5. Add password strength requirements

---

### D-10: Basket Total Incorrect for Duplicate Items

**Defect ID:** D-10  
**Test Case:** SSWA-23 - Verify Basket Total Calculation  
**Reported Date:** 2026-02-04  
**Severity:** Critical  
**Priority:** P1  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
When the same product is added multiple times to basket, total only shows price of single item instead of price × quantity.

**Description:**  
When the same product is added to the basket multiple times, the total calculation only includes the price of one item instead of multiplying by quantity. For example, adding 2x items at £1.00 each should show £2.00, but the system only shows £1.00. The basket is not properly calculating (price × quantity) for duplicate items.

**Steps to Reproduce:**
1. Navigate to Browse Sweets page
2. Add a product to basket (e.g., Chocolate Cups - £1.00)
3. Add the same product again (quantity becomes 2)
4. Navigate to Basket page
5. Observe the total calculation

**Expected Result:**
- Basket shows: Chocolate Cups x 2
- Quantity displayed: 2
- Expected total: £2.00 (£1.00 × 2)
- Calculation formula: price × quantity per item

**Actual Result:**
- Basket shows: Chocolate Cups x 2
- Quantity displayed: 2
- Actual total: £1.00 (only single item price)
- Total calculation completely ignores quantity multiplier
- Formula appears to be: price (not price × quantity)

**Evidence:**
- Screenshot showing quantity 2 but total £1.00
- File: item_total_issue.png

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10
- Test Products: Chocolate Cups (£1.00), Bon Bons (£1.00)

**Impact:**
- **Revenue Loss:** Customers charged incorrectly (undercharged)
- **Business Logic:** Critical calculation error in e-commerce flow
- **Order Processing:** All orders with multiple quantities are affected
- **Financial:** Direct revenue impact for every duplicate item order

**Root Cause:**
- JavaScript calculation logic error in basket total function
- Missing quantity multiplication in total calculation
- Function likely sums item.price instead of item.price * item.quantity

**Technical Details:**
```javascript
// Likely current implementation (incorrect):
total = items.reduce((sum, item) => sum + item.price, 0);

// Should be:
total = items.reduce((sum, item) => sum + (item.price * item.quantity), 0);
```

**Recommendation:**
1. Update basket calculation to include quantity: `price * quantity`
2. Add unit tests for basket calculations
3. Test with various quantities (1, 2, 5, 10)
4. Verify calculation across all product types
5. Add validation to ensure quantity is always considered

---

### D-12: Checkout Button Does Not Navigate

**Defect ID:** D-12  
**Test Case:** SSWA-32 - Verify Continue to Checkout Button  
**Reported Date:** 2026-02-04  
**Severity:** Critical  
**Priority:** P1  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
The "Continue to checkout" button reloads the page instead of navigating to checkout confirmation, preventing order completion.

**Description:**  
The "Continue to checkout" button is clickable but does not navigate to a checkout confirmation or payment processing page as expected. Instead, it simply reloads the current basket page. This prevents users from completing their purchase. The form has no action attribute defined.

**Steps to Reproduce:**
1. Add items to basket
2. Navigate to Basket page
3. Fill in billing address fields (name, email, address)
4. Fill in payment information fields (card number, CVV, expiration)
5. Select delivery option
6. Click "Continue to checkout" button

**Expected Result:**
- Form submits to checkout processing endpoint
- User navigates to order confirmation page
- Order details are processed
- Confirmation page shows order summary
- User receives order confirmation

**Actual Result:**
- Clicking button causes page to reload
- Returns to basket page (same page)
- No navigation occurs
- No order processing happens
- Form data is cleared
- User cannot complete checkout
- Stuck in infinite loop on basket page

**Evidence:**
- Screenshot showing button and page reload
- Network tab shows no POST request to checkout endpoint
- File: checkout_button_issue.png

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **Business Critical:** COMPLETE FAILURE of checkout process
- **Revenue:** ZERO orders can be completed - 100% revenue loss
- **User Experience:** Extremely frustrating - users cannot buy products
- **Conversion Rate:** 0% - no purchases possible

**Root Cause:**
- Form missing `action` attribute
- Button type may be incorrect (type="button" instead of type="submit")
- Missing form submission handler
- No checkout endpoint configured

**Technical Details:**
```html
<!-- Likely current implementation: -->
<form>
  <button type="button">Continue to checkout</button>
</form>

<!-- Should be: -->
<form action="/checkout" method="POST">
  <button type="submit">Continue to checkout</button>
</form>
```

**Recommendation:**
1. Add form `action` attribute pointing to checkout endpoint
2. Ensure button `type="submit"`
3. Implement checkout processing logic
4. Add form validation before submission
5. Create order confirmation page
6. Implement proper form handling

---

### D-13: Total Shows NaN on Delivery Change

**Defect ID:** D-13  
**Test Case:** SSWA-34 - Test Total Recalculation on Delivery Change  
**Reported Date:** 2026-02-04  
**Severity:** Critical  
**Priority:** P1  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
Selecting "Standard Shipping" delivery option causes basket total to display "NaN" instead of recalculating correctly.

**Description:**  
Selecting the Standard Shipping (£1.99) option triggers a recalculation of the basket total. Although the shipping value itself is numeric, the calculation fails due to improper handling of numeric data within the getCartDetails() function. One or more values used in the calculation (such as the basket subtotal) are treated as strings or undefined, causing the arithmetic operation to return NaN. No JavaScript error is thrown in the console, as NaN is produced silently.

**Steps to Reproduce:**
1. Add items to basket (e.g., 2 items totaling £2.00)
2. Navigate to Basket page
3. Observe current total with "Collect (FREE)" selected - total displays £2.00
4. Click "Standard Shipping (£1.99)" radio button
5. Observe total field

**Expected Result:**
- Total recalculates when shipping option changes
- Calculation: £2.00 (subtotal) + £1.99 (shipping) = £3.99
- Total displays: "£3.99"
- Total is a valid number

**Actual Result:**
- Total immediately changes to "NaN"
- Display shows: "Total (GBP) NaN"
- Total becomes completely unusable
- Cannot proceed with checkout
- Switching back to "Collect (FREE)" still shows "NaN"
- Total never recovers

**Evidence:**
- Screenshot showing "NaN" in total field
- File: shipping_total_issue.png

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **Checkout Blocked:** Users cannot complete purchase with shipping
- **User Experience:** Confusing and unprofessional
- **Revenue Loss:** Users who need shipping cannot order
- **Data Integrity:** Calculation logic fundamentally broken

**Root Cause:**
- JavaScript type coercion error
- String concatenation instead of numeric addition
- Missing parseFloat() or Number() conversion
- Function getCartDetails() has improper data type handling

**Technical Details:**
```javascript
// Likely issue in getCartDetails() function:
// Subtotal stored as string: "2.00"
// Shipping as number: 1.99
// Operation: "2.00" + 1.99 = NaN (invalid operation)

// Should be:
const subtotal = parseFloat(basketSubtotal);
const shipping = parseFloat(shippingCost);
const total = subtotal + shipping;
```

**Console Errors:**
- No console errors thrown (NaN produced silently)
- Silent failure makes debugging difficult

**Recommendation:**
1. Add parseFloat() or Number() to ensure numeric types
2. Validate all values before arithmetic operations
3. Add error handling for NaN results
4. Display user-friendly error message if calculation fails
5. Add console.log for debugging calculation steps
6. Implement input validation for all numeric fields
7. Add unit tests for calculation functions

---

## High Severity Defects

### D-3: Wham Bar Product Image Missing - 404 Error

**Defect ID:** D-3  
**Test Case:** SSWA-4 - Verify All Product Cards Displayed Correctly  
**Reported Date:** 2026-02-01  
**Severity:** High  
**Priority:** P2  
**Status:** Open  
**Module:** Browse Sweets Page

**Summary:**  
Wham Bar product image fails to load due to incorrect filename in the code (typo: whan.jpg instead of wham.jpg).

**Description:**  
The Wham Bar product image fails to load on the Browse Sweets page due to an incorrect filename in the code. The image source references "whan.jpg" when it should be "wham.jpg" - a simple typo in the filename.

**Steps to Reproduce:**
1. Navigate to Browse Sweets page
2. Scroll through product grid
3. Locate "Wham Bar" product card
4. Observe product image area

**Expected Result:**
- Product image for Wham Bar displays correctly
- Image shows the actual Wham Bar candy
- No broken image icon
- Consistent with other product cards

**Actual Result:**
- Broken image icon displayed
- Alt text visible: "wham bar"
- Image does not load
- Console error: GET https://sweetshop.vivrichards.co.uk/img/whan.jpg 404 (Not Found)
- Network tab shows: whan.jpg - Status 404

**Evidence:**
- Screenshots: BUG-001.png, BUG-001(1).png, BUG-001(2).png
- Console error message
- Network request showing 404

**Technical Details:**
- **Incorrect filename:** whan.jpg
- **Correct filename:** wham.jpg
- **Error location:** sweets:188 (line 188 in sweets page code)
- **HTTP Status:** 404 Not Found
- **Image path:** /img/whan.jpg

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **User Experience:** Unprofessional appearance
- **Product Display:** Wham Bar product not properly showcased
- **Brand Image:** Reduces trust in website quality
- **Sales:** May reduce conversions for this product

**Root Cause:**
- Typo in HTML image source attribute
- File exists as "wham.jpg" but code references "whan.jpg"

**Fix:**
```html
<!-- Current (incorrect): -->
<img src="img/whan.jpg" alt="wham bar">

<!-- Should be (correct): -->
<img src="img/wham.jpg" alt="wham bar">
```

**Recommendation:**
1. Correct filename typo in HTML: change "whan.jpg" to "wham.jpg"
2. Verify image file exists at correct path
3. Test image loads correctly after fix
4. Audit all product images for similar issues
5. Implement automated image validation tests

---

### D-4: Product Prices Not Aligned Consistently

**Defect ID:** D-4  
**Test Case:** SSWA-6 - Verify Product Grid Responsiveness  
**Reported Date:** 2026-02-04  
**Severity:** Medium  
**Priority:** P2  
**Status:** Open  
**Module:** Browse Sweets Page

**Summary:**  
Product prices are not consistently aligned across product cards on all device sizes (desktop, tablet, mobile).

**Description:**  
Product prices are not consistently aligned across product cards on any device size (desktop, tablet, mobile). Some prices appear higher or lower than others, creating an inconsistent and unprofessional user interface. The CSS for price positioning is not standardized across all product cards, affecting the visual hierarchy and readability.

**Steps to Reproduce:**
1. Navigate to Browse Sweets page
2. Open Chrome DevTools (F12)
3. Enter Responsive Design Mode (Ctrl+Shift+M)
4. Test on Desktop view (1920x1080)
5. Test on Tablet view (768x1024)
6. Test on Mobile view (375x667)
7. Observe price alignment across all product cards

**Expected Result:**
- All product prices aligned horizontally at same level
- Consistent vertical positioning within each card
- Prices appear on same baseline across the grid
- Professional, organized appearance
- Alignment maintained across all screen sizes

**Actual Result:**
- Prices positioned inconsistently
- Some prices appear 5-15 pixels higher or lower than others
- No discernible pattern to the misalignment
- Appears random across different products
- Issue occurs on ALL device sizes:
  - Desktop (1920x1080): Misaligned
  - Tablet (768x1024): Misaligned
  - Mobile (375x667): Misaligned

**Evidence:**
- Screenshot: image.png
- Visual comparison showing price misalignment

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10
- Tested Resolutions: 1920x1080, 768x1024, 375x667

**Impact:**
- **User Experience:** Unprofessional appearance
- **Visual Design:** Lacks polish and attention to detail
- **Brand Perception:** Reduces trust in website quality
- **Readability:** Harder to quickly compare prices

**Root Cause:**
- Inconsistent CSS for price elements
- Missing flexbox or grid alignment properties
- Variable content lengths pushing prices to different positions
- No baseline alignment enforced

**Technical Details:**
```css
/* Likely missing or inconsistent: */
.product-card {
  display: flex;
  flex-direction: column;
}

.product-price {
  margin-top: auto; /* Push to bottom */
  align-self: baseline; /* Align consistently */
}
```

**Recommendation:**
1. Standardize CSS for all product price elements
2. Use flexbox with `margin-top: auto` to push prices to bottom
3. Ensure consistent padding/margins on price elements
4. Set min-height on product description to prevent layout shift
5. Test alignment across all products after fix
6. Add CSS class for price positioning
7. Implement visual regression testing

---

### D-5: About Page Navigation Returns 404 Error

**Defect ID:** D-5  
**Test Case:** SSWA-8 - Verify Navigation to About Page  
**Reported Date:** 2026-02-03  
**Severity:** High  
**Priority:** P2  
**Status:** Open  
**Module:** About Page

**Summary:**  
Clicking "About" link from certain pages (e.g., Basket) results in 404 error due to routing typo (requests "/bout" instead of "/about").

**Description:**  
When navigating from the Basket page to the About page using the navigation menu, the application displays a "Page Not Found" error. The Network tab shows the request is looking for "bout" instead of "about" - this is a URL routing error with a typo in the route path. The link is misconfigured.

**Steps to Reproduce:**
1. Navigate to Basket page (https://sweetshop.vivrichards.co.uk/basket.html)
2. Click "About" link in the top navigation menu
3. Observe page response

**Expected Result:**
- "About" link is clickable
- User is redirected to About page
- URL changes to: /about.html or /about
- About page content loads successfully
- No errors displayed

**Actual Result:**
- Page displays "404 - Page Not Found" error
- URL shows: /bout (missing "a")
- Console error: Failed to load resource: the server responded with a status of 404 ()
- Network tab shows: Request for "bout" returns 404 (Doc type)
- User cannot access About page from this navigation path

**Evidence:**
- Console error screenshot
- Network tab showing 404 for "bout" request

**Technical Details:**
- **Incorrect route:** /bout
- **Correct route:** /about
- **Error type:** URL routing error / typo in href attribute
- **Affected from:** Basket page navigation
- **May also affect:** Other pages (needs verification)

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **Navigation Broken:** Users cannot access About page information
- **User Experience:** Frustrating dead-end for users
- **Information Access:** Company/project details not accessible
- **SEO:** 404 errors negatively impact search rankings

**Root Cause:**
- Typo in navigation link href attribute
- Missing "a" in "about"

**Fix:**
```html
<!-- Current (incorrect): -->
<a href="bout.html">About</a>

<!-- Should be (correct): -->
<a href="about.html">About</a>
```

**Recommendation:**
1. Fix typo in href: change "bout.html" to "about.html"
2. Test navigation from all pages
3. Audit all navigation links for similar typos
4. Implement link validation in testing
5. Add automated navigation tests
6. Check if issue exists on other pages

---

### D-8: Email Validation Accepts Invalid Formats

**Defect ID:** D-8  
**Test Case:** SSWA-16 - Test Login with Invalid Email  
**Reported Date:** 2026-02-04  
**Severity:** High  
**Priority:** P2  
**Status:** Open  
**Module:** Login Functionality

**Summary:**  
Email field validation only checks for "@" symbol presence, accepting invalid email formats like "test@a" or "user@1".

**Description:**  
Email field validation only checks for the presence of "@" symbol followed by any character, accepting improperly formatted email addresses. Valid email format requires "@" followed by a domain name with proper structure (e.g., domain.com). Current validation accepts emails like "test@a" or "user@1" which are not valid email addresses.

**Steps to Reproduce:**
1. Navigate to Login page
2. Enter invalid email format:
   - "test@a"
   - "user@1"
   - "anything@x"
   - "email@"
3. Enter any password
4. Click Login button

**Expected Result:**
- Validation error appears
- Error message: "Invalid email format" or "Please enter a valid email"
- Form is not submitted
- User remains on Login page
- Field shows error state (red border, error icon)

**Actual Result:**
- System accepts any string with "@" + any character(s)
- No validation error for:
  - "test@a" (no domain)
  - "user@1" (numeric domain)
  - "anything@x" (single letter domain)
- No TLD validation (.com, .org, etc.)
- No domain structure validation
- Form submits successfully with invalid emails
- Login proceeds (due to no authentication - see D-7)

**Evidence:**
- Screen recording showing acceptance of invalid emails
- File: Recording_email_validation.mp4

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **Data Quality:** Invalid email addresses stored in database
- **Email Delivery:** Confirmation emails will fail to send
- **User Communication:** Cannot contact users with invalid emails
- **User Experience:** Users may enter incorrect emails by mistake
- **Business Operations:** Marketing emails will bounce

**Root Cause:**
- Weak regex pattern or validation logic
- Only checks for "@" symbol presence
- Missing domain and TLD validation

**Current vs Expected Validation:**
```javascript
// Current (weak):
email.includes('@')

// Should be (strong):
/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)
// Or use HTML5 type="email" with additional JS validation
```

**Recommendation:**
1. Implement proper email validation regex
2. Validate domain structure (at least 2 parts: domain.tld)
3. Require valid TLD (.com, .org, .net, etc.)
4. Use HTML5 type="email" as first layer
5. Add JavaScript validation as second layer
6. Display clear error messages
7. Consider email verification flow (send verification email)

---

## Medium Severity Defects

### D-6: Social Login Icons Non-Functional

**Defect ID:** D-6  
**Test Case:** SSWA-13 - Verify Social Login Options  
**Reported Date:** 2026-02-04  
**Severity:** Medium  
**Priority:** P3  
**Status:** Open  
**Module:** Login Functionality

**Summary:**  
Social media login icons (Twitter, Facebook, LinkedIn) are displayed but completely non-functional - clicking them reloads the page.

**Description:**  
The social login icons (Twitter, Facebook, LinkedIn) on the Login page are displayed but completely non-functional. When clicked, instead of redirecting to the respective social media authentication pages, the current page simply reloads. This suggests the icons are either missing their href attributes, have broken links, or the click event handlers are not properly implemented.

**Steps to Reproduce:**
1. Navigate to Login page
2. Scroll below the Login button
3. Observe three social media icons (Twitter, Facebook, LinkedIn)
4. Click on Twitter icon
5. Click on Facebook icon
6. Click on LinkedIn icon

**Expected Result:**
- Clicking Twitter icon redirects to Twitter OAuth authentication
- Clicking Facebook icon redirects to Facebook Login
- Clicking LinkedIn icon redirects to LinkedIn authentication
- New window/tab opens for social login
- User can authenticate via social media
- Returns to application after successful authentication

**Actual Result:**
- Clicking any icon causes page reload
- No redirection occurs
- No new window/tab opens
- Icons appear clickable but do nothing
- Page returns to same Login page
- No console errors
- No network requests for OAuth

**Evidence:**
- Screenshot: login_icons.png
- No network activity when icons clicked

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **User Experience:** Misleading UI - icons appear functional but aren't
- **Alternative Login:** Users cannot use social login option
- **Convenience:** Forces users to create separate account
- **Conversion:** May reduce signups (social login is easier)

**Root Cause:**
- Missing href attributes in anchor tags
- No OAuth integration implemented
- Click handlers not configured
- Social authentication not set up

**Technical Details:**
```html
<!-- Likely current: -->
<a href="#"><img src="twitter-icon.png"></a>
<!-- or -->
<a href=""><img src="twitter-icon.png"></a>

<!-- Should be: -->
<a href="/auth/twitter"><img src="twitter-icon.png"></a>
<!-- or with OAuth flow -->
```

**Recommendation:**
1. If social login not implemented: Remove icons or add "Coming Soon"
2. If implemented: Fix href to point to OAuth endpoints
3. Implement proper OAuth 2.0 flow for each platform
4. Add click handlers to initiate authentication
5. Test OAuth flow end-to-end
6. Consider disabling icons until feature is ready

---

### D-11: Promo Code Field Non-Functional

**Defect ID:** D-11  
**Test Case:** SSWA-31 - Test Promo Code Application  
**Reported Date:** 2026-02-04  
**Severity:** Medium  
**Priority:** P3  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
Promo code feature completely non-functional - no validation, no response, no error messages when code entered and redeemed.

**Description:**  
The promo code redemption feature is completely non-functional. No promo codes are provided anywhere in the application, and when any test code is entered and "Redeem" clicked, nothing happens - no error message, no success message, no total change. There is no user feedback at all, suggesting the backend validation or the button event handler is not implemented.

**Steps to Reproduce:**
1. Add items to basket
2. Navigate to Basket page
3. Locate promo code section
4. Enter test code: "TEST123"
5. Click "Redeem" button
6. Try other codes: "DISCOUNT10", "SAVE20", "PROMO"
7. Observe response

**Expected Result:**
- System validates promo code
- If valid: Discount applied, total recalculated, success message
- If invalid: Error message "Invalid promo code"
- Visual feedback (loading spinner, success/error state)
- Total updates if discount applied

**Actual Result:**
- Entering any code and clicking Redeem: NO response
- No error message
- No success message
- No change to total
- No visual feedback
- No console errors
- No network requests
- Complete silence - feature appears broken

**Evidence:**
- Testing multiple codes showed no response
- No network activity in DevTools

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **Revenue:** Cannot offer promotional discounts
- **Marketing:** Promotional campaigns cannot be run
- **User Experience:** Frustrating for users with valid codes
- **Competitive:** Cannot match competitor promotions

**Root Cause:**
- Redeem button handler not implemented
- No backend validation endpoint
- No promo code database/system
- Feature partially built but not functional

**Technical Details:**
```javascript
// Likely missing:
function redeemPromoCode() {
  const code = document.getElementById('promo-code').value;
  // No implementation here
}

// Should have:
- API call to validate code
- Success/error handling
- Total recalculation
- User feedback
```

**Recommendation:**
1. If feature not ready: Hide promo code section until implemented
2. Implement promo code validation system
3. Create promo code database/configuration
4. Add API endpoint for code validation
5. Implement discount calculation logic
6. Add user feedback (success/error messages)
7. Test with valid and invalid codes

---

### D-14: Credit Card Field Accepts Invalid Input

**Defect ID:** D-14  
**Test Case:** SSWA-35 - Verify Credit Card Number Field Validation  
**Reported Date:** 2026-02-04  
**Severity:** Medium  
**Priority:** P3  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
Credit card number field accepts letters, symbols, and invalid lengths - no proper validation for card number format.

**Description:**  
The credit card field allows typing letters, symbols, and numbers of any length up to 19 digits. However, the form does not submit because HTML5 validation (required and maxlength) prevents submission. No numeric-only or Luhn algorithm validation is implemented, which may confuse users and could allow invalid input if server-side checks are not in place.

**Steps to Reproduce:**
1. Navigate to Basket page
2. Scroll to Payment section
3. Click on credit card number field
4. Try entering: "abcdefgh" (letters)
5. Try entering: "!@#$%^&*" (symbols)
6. Try entering: "abc123!@#" (mixed)
7. Try entering: "123" (too short)
8. Try entering: "12345678901234567890" (too long)

**Expected Result:**
- Field only accepts numeric input (0-9)
- Field validates card number length (13-19 digits)
- Luhn algorithm validation for card number validity
- Real-time validation as user types
- Clear error message for invalid input
- Visual feedback (red border, error icon)

**Actual Result:**
- Field accepts letters: "abcdefgh"
- Field accepts special characters: "!@#$%^&*"
- Field accepts mixed input: "abc123!@#"
- Field accepts any length
- No numeric-only restriction
- No Luhn algorithm check
- No real-time validation
- Form won't submit (HTML5 validation prevents) but no clear error

**Evidence:**
- Screenshot: cc_number.png
- Shows field accepting invalid characters

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **User Experience:** Confusing - allows invalid input but prevents submission
- **Data Quality:** Could allow invalid cards if server validation missing
- **User Frustration:** No clear feedback on what's wrong
- **Payment Processing:** Risk of invalid payment attempts

**Root Cause:**
- Missing input type restriction
- No pattern attribute for numeric-only
- No JavaScript validation
- No Luhn algorithm implementation

**Technical Details:**
```html
<!-- Current (weak): -->
<input type="text" maxlength="19" required>

<!-- Should be: -->
<input type="text" 
       pattern="[0-9]{13,19}" 
       maxlength="19" 
       required
       oninput="this.value = this.value.replace(/[^0-9]/g, '')">

<!-- Plus JavaScript Luhn validation -->
```

**Recommendation:**
1. Add pattern="[0-9]{13,19}" to accept only numbers
2. Add oninput handler to filter non-numeric characters
3. Implement Luhn algorithm validation
4. Add real-time validation feedback
5. Format display: XXXX XXXX XXXX XXXX
6. Show card type icon (Visa, Mastercard, etc.)
7. Provide clear error messages

---

### D-15: CVV Field Has Number Spinner with Negative Values

**Defect ID:** D-15  
**Test Case:** SSWA-36 - Test CVV Field Input Restrictions  
**Reported Date:** 2026-02-04  
**Severity:** Medium  
**Priority:** P3  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
CVV field implemented as type="number" shows spinner controls allowing negative values and unlimited length.

**Description:**  
The CVV field is implemented as type="number", which displays up/down spinners. Users can click the down arrow or manually type negative numbers, which is invalid for CVV. There is no restriction on input length or numeric range, allowing CVVs of 1-5 digits or negative values. Proper validation should enforce 3-4 positive digits only, either using type="text" with a regex pattern or type="number" with min/max constraints.

**Steps to Reproduce:**
1. Navigate to Basket page
2. Scroll to Payment section
3. Click on CVV field
4. Observe up/down arrow spinners
5. Click down arrow multiple times
6. Observe negative numbers: -1, -2, -123
7. Type directly: -999
8. Type 5 digits: 12345
9. Type 1 digit: 1

**Expected Result:**
- Field accepts 3-4 digits only
- No negative numbers allowed
- No spinner controls visible
- Only positive integers 3-4 digits long
- Input restricted immediately (cannot type invalid)

**Actual Result:**
- Up/down spinner controls visible
- Can click down to create negative: -1, -123, -999
- Can manually type negative values
- No restriction on length (allows 1-5+ digits)
- Spinner encourages clicking instead of typing
- No min/max constraints

**Evidence:**
- Screenshot: cvv.png
- Shows spinner controls and negative value

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **User Experience:** Spinner is confusing for CVV field
- **Data Validation:** Allows invalid CVV formats
- **Payment Processing:** Risk of payment errors
- **Usability:** Users might accidentally use spinner

**Root Cause:**
- Using type="number" instead of type="text"
- Missing min/max attributes
- No pattern validation

**Technical Details:**
```html
<!-- Current (incorrect): -->
<input type="number">

<!-- Should be (Option 1 - recommended): -->
<input type="text" 
       pattern="[0-9]{3,4}" 
       maxlength="4"
       oninput="this.value = this.value.replace(/[^0-9]/g, '')">

<!-- Should be (Option 2): -->
<input type="number" 
       min="0" 
       max="9999"
       oninput="if(this.value.length > 4) this.value = this.value.slice(0,4)">
```

**Recommendation:**
1. Change type to "text" with pattern validation
2. Or keep type="number" but add min="0" and max="9999"
3. Remove spinner controls with CSS: `-webkit-appearance: none;`
4. Restrict length to 3-4 digits
5. Prevent negative numbers
6. Add placeholder: "123" or "1234"
7. Add tooltip explaining CVV location

---

### D-16: Billing Email Accepts Invalid Format

**Defect ID:** D-16  
**Test Case:** SSWA-37 - Verify Email Field Validation in Billing  
**Reported Date:** 2026-02-04  
**Severity:** Medium  
**Priority:** P3  
**Status:** Open  
**Module:** Shopping Basket

**Summary:**  
Billing email field validation accepts invalid formats like "user@x" - missing proper TLD and domain validation.

**Description:**  
The billing email field uses type="email", which enforces basic HTML5 validation. Inputs like "test@" are rejected (checkValidity() returns false). However, the field does not enforce a proper domain or top-level domain (TLD), so inputs like "user@x" are still accepted. This weak validation could allow technically invalid email addresses, potentially causing issues with order confirmations and customer communication.

**Steps to Reproduce:**
1. Navigate to Basket page with items
2. Scroll to Billing Address section
3. Click on Email field
4. Enter invalid emails:
   - "user@x"
   - "test@a"
   - "email@1"
   - "customer@ab"
5. Tab out or attempt form submission

**Expected Result:**
- Validation rejects emails without proper TLD
- Error message: "Please enter a valid email address"
- Requires format: username@domain.extension
- Domain must have at least 2 parts
- TLD must be valid (.com, .org, .net, etc.)

**Actual Result:**
- HTML5 validation rejects: "test@" (incomplete)
- But ACCEPTS:
  - "user@x" (single letter domain)
  - "email@1" (numeric domain)
  - "customer@ab" (no TLD)
- No validation for:
  - Proper domain structure
  - Valid TLD requirement
  - Domain length

**Evidence:**
- Screenshot: email.png
- Shows acceptance of "user@x"

**Environment:**
- Browser: Chrome (Latest)
- OS: Windows 10

**Impact:**
- **Order Confirmation:** Emails will fail to send
- **Customer Communication:** Cannot contact customers
- **Data Quality:** Invalid emails in database
- **Business Operations:** Support unable to reach customers

**Root Cause:**
- Relying only on HTML5 type="email" validation
- Missing additional JavaScript validation
- No domain/TLD verification

**Technical Details:**
```javascript
// HTML5 validation (current):
// Accepts: user@x, test@1, etc.

// Should add JavaScript:
function validateEmail(email) {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]{2,}$/;
  return regex.test(email);
}

// Or stricter:
const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
```

**Recommendation:**
1. Add JavaScript validation on top of HTML5
2. Require proper domain with at least 2 parts
3. Validate TLD is at least 2 characters
4. Consider email verification (send confirmation email)
5. Add real-time validation feedback
6. Show clear error messages
7. Suggest corrections (e.g., "Did you mean @gmail.com?")

---

## Defect Statistics

### Finding Timeline

| Date | Defects Found | Critical | High | Medium |
|------|---------------|----------|------|--------|
| 2026-02-01 | 2 | 0 | 1 | 1 |
| 2026-02-03 | 1 | 0 | 1 | 0 |
| 2026-02-04 | 13 | 5 | 2 | 6 |

### Module Impact Analysis

**Most Critical Module:** Shopping Basket
- 9 defects total
- 3 critical defects (checkout failures)
- Blocks entire purchase workflow

**Most Defects:** Shopping Basket (9 defects)
**Highest Severity:** Login Functionality (2 critical security issues)

### Defect Priority Summary

| Priority | Description | Count | Action Required |
|----------|-------------|-------|-----------------|
| P1 | Fix Immediately - Blocking | 5 | Deploy hotfix within 24 hours |
| P2 | Fix in Next Release | 4 | Include in next sprint |
| P3 | Fix When Possible | 7 | Backlog prioritization |

---

## Recommendations

### Immediate Actions (P1 - Critical)

1. **D-7, D-9:** Implement authentication system ASAP
2. **D-10:** Fix basket calculation for quantity
3. **D-12:** Fix checkout button navigation
4. **D-13:** Fix NaN issue in delivery calculation

### Next Release (P2 - High)

1. **D-3:** Fix Wham Bar image filename typo
2. **D-4:** Standardize price alignment CSS
3. **D-5:** Fix About page routing
4. **D-8:** Implement proper email validation

### Backlog (P3 - Medium)

1. Review all medium priority defects
2. Prioritize based on business impact
3. Schedule for future sprints
4. Consider removing non-functional features (social login, promo code)

---

## Testing Tools Used

- **Browser:** Google Chrome (Latest)
- **Chrome DevTools:**
  - Console (JavaScript errors)
  - Network (Request/Response monitoring)
  - Elements (HTML/CSS inspection)
  - Application (Storage/Cookies)
- **Test Management:** Qase Platform
- **Evidence:** Screenshots, Screen Recordings

---

**Report Generated:** February 4, 2026  
**Report Version:** 1.0  
**Next Review:** After defect fixes deployed
