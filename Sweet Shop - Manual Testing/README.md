# Sweet Shop Web Application - Manual Testing Project

![Testing](https://img.shields.io/badge/Testing-Manual-blue)
![Chrome DevTools](https://img.shields.io/badge/Tools-Chrome_DevTools-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Project Overview

This repository contains comprehensive manual testing documentation for the **Sweet Shop Web Application** - an intentionally broken e-commerce application designed to demonstrate Chrome DevTools and common web application issues.

- **Application URL:** [https://sweetshop.vivrichards.co.uk/](https://sweetshop.vivrichards.co.uk/)
- **Testing Period:** February 1-4, 2026
- **Tester:** Pragati Nangare
- **Test Management Platform:** Qase

---

## 🎯 Testing Objectives

- Validate core e-commerce functionality (browse, login, checkout)
- Identify UI/UX issues and inconsistencies
- Verify form validations and security measures
- Test cross-browser compatibility and responsiveness
- Ensure accessibility standards compliance
- Document defects with detailed reproduction steps

---

## 🛠️ Testing Approach

### Methodology
- **Manual Testing** with Chrome DevTools integration
- **Black Box Testing** approach
- **Exploratory Testing** combined with scripted test cases
- **Defect-driven Testing** focusing on intentional bugs

### Tools Used
- **Browser:** Google Chrome (Latest version)
- **DevTools Features:**
  - Console (JavaScript errors)
  - Network (Request/Response monitoring)
  - Elements (HTML/CSS inspection)
  - Application (Storage/Cookies)
  - Responsive Design Mode (Mobile testing)
- **Test Management:** Qase Platform
- **Documentation:** Markdown, Screenshots, Screen Recordings

---

## 📊 Test Execution Summary

### Test Statistics

| Metric | Count |
|--------|-------|
| **Total Test Cases** | 37 |
| **Test Cases Passed** | 22 |
| **Test Cases Failed** | 15 |
| **Pass Rate** | 59.5% |
| **Defects Found** | 16 |

### Test Coverage by Module

| Module | Test Cases | Passed | Failed |
|--------|------------|--------|--------|
| Browse Sweets Page | 5 | 3 | 2 |
| About Page | 2 | 1 | 1 |
| Login Functionality | 12 | 8 | 4 |
| Shopping Basket | 18 | 10 | 7 |

### Defects by Severity

| Severity | Count | Percentage |
|----------|-------|------------|
| **Critical** | 5 | 31.25% |
| **High** | 4 | 25% |
| **Medium** | 7 | 43.75% |
| **Total** | 16 | 100% |

---

## 🧪 Test Suites

### 1. Browse Sweets Page (5 Test Cases)
**Focus:** Product catalog, navigation, responsive design

**Key Test Cases:**
- Page layout verification
- Navigation menu elements
- Product card display
- Basket counter functionality
- Responsive grid layout

### 2. About Page (2 Test Cases)
**Focus:** Informational content and navigation

**Key Test Cases:**
- Page content verification
- Navigation accessibility

### 3. Login Functionality (12 Test Cases)
**Focus:** Authentication and form validation

**Key Test Cases:**
- Login page layout
- Email/Password field validation
- Valid/Invalid credentials testing
- Social login options
- Security testing (password masking, XSS, SQL injection)
- Accessibility (keyboard navigation)

### 4. Shopping Basket (18 Test Cases)
**Focus:** E-commerce checkout workflow

**Key Test Cases:**
- Basket page layout
- Item management (add/delete)
- Total calculation accuracy
- Billing address forms
- Payment field validation
- Delivery options
- Promo code functionality
- Checkout process

---

## 🐛 Critical Defects Found

### 1. Authentication Bypass (Critical)
- **Defect ID:** D-7
- **Issue:** Login accepts any credentials without validation
- **Impact:** Complete security bypass

### 2. Basket Calculation Error (Critical)
- **Defect ID:** D-10
- **Issue:** Total only shows price of 1 item when multiple quantities added
- **Impact:** Revenue loss, incorrect pricing

### 3. Checkout Failure (Critical)
- **Defect ID:** D-12
- **Issue:** Checkout button reloads page instead of processing order
- **Impact:** Users cannot complete purchases

### 4. NaN in Total (Critical)
- **Defect ID:** D-13
- **Issue:** Selecting shipping option shows "NaN" as total
- **Impact:** Checkout impossible with shipping

### 5. No Password Validation (Critical)
- **Defect ID:** D-9
- **Issue:** Any password accepted for any email
- **Impact:** Account security compromised

---

## 📸 Evidence Collection

All defects include:
- ✅ Detailed reproduction steps
- ✅ Screenshots showing the issue
- ✅ Console errors (where applicable)
- ✅ Network logs (for failed requests)
- ✅ Screen recordings (for complex workflows)

---

## 🔍 Chrome DevTools Usage

### Console Tab
- Monitored JavaScript errors and warnings
- Identified missing resources (404 errors)
- Tracked function execution issues

### Network Tab
- Analyzed HTTP requests/responses
- Identified failed resource loads
- Measured page load performance
- Detected routing errors (404s)

### Elements Tab
- Inspected HTML structure
- Verified CSS styling issues
- Checked alignment problems
- Examined form attributes

### Application Tab
- Checked session storage
- Monitored cookie behavior
- Verified basket data persistence

### Responsive Design Mode
- Tested mobile viewport (375x667)
- Tested tablet viewport (768x1024)
- Tested desktop viewport (1920x1080)

---

## 📝 Key Findings

### Security Issues
1. No authentication mechanism
2. Weak email validation
3. No password strength requirements
4. Accepts invalid input formats

### Functional Issues
1. Broken navigation (About page 404)
2. Incorrect basket calculations
3. Non-functional checkout process
4. Promo code feature not implemented

### UI/UX Issues
1. Inconsistent price alignment
2. Missing product images
3. Non-functional social login icons
4. Poor form validation feedback

### Data Validation Issues
1. Credit card field accepts letters/symbols
2. CVV field allows negative numbers
3. Email validation accepts invalid formats
4. No input length restrictions

---

## 🎓 Skills Demonstrated

- **Manual Testing Expertise:** Comprehensive test case design and execution
- **Chrome DevTools Proficiency:** Effective use of Console, Network, Elements, and Application tabs
- **Defect Reporting:** Clear, detailed bug documentation with reproduction steps
- **Test Documentation:** Professional markdown documentation for GitHub
- **E-commerce Testing:** Understanding of online shopping workflows
- **Security Testing:** Basic validation testing (XSS, SQL injection attempts)
- **Responsive Testing:** Cross-device and cross-browser validation
- **Test Management:** Qase platform utilization

---

## 🚀 How to Use This Repository

### For Recruiters/Hiring Managers
1. Review `TEST_CASES.md` to see comprehensive test coverage
2. Check `DEFECT_REPORT.md` for detailed defect analysis
3. Assess testing methodology and documentation quality
4. Evaluate Chrome DevTools usage and technical skills

### For QA Professionals
1. Use test cases as templates for similar projects
2. Reference defect reporting format
3. Learn Chrome DevTools techniques
4. Understand manual testing best practices

### For Learners
1. Study the systematic testing approach
2. Learn how to use Chrome DevTools for testing
3. Understand defect severity classification
4. See real-world testing documentation examples

---

## 📧 Contact

**Tester:** Pragati Nangare  
**LinkedIn:** [https://www.linkedin.com/in/pragati-nangare-b00033239/](https://www.linkedin.com/in/pragati-nangare-b00033239/)  
**Email:** pragatin123@gmail.com

---

## 📄 License

This testing documentation is created for educational and portfolio purposes.

---

## 🙏 Acknowledgments

- **Sweet Shop Application:** Created by Viv Richards as a Chrome DevTools demonstration tool
- **Qase Platform:** For test management capabilities
- **Chrome DevTools:** For providing comprehensive testing and debugging tools

---

## 📌 Notes

This is a **demo/training application** intentionally designed with bugs to demonstrate testing and DevTools usage. The defects found are expected and serve as learning opportunities for testers and developers.

**Last Updated:** February 4, 2026
