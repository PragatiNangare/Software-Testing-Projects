# AgileWay Travel – Manual Testing Project

## Project Overview
This project demonstrates end-to-end **manual testing** of the AgileWay Travel flight booking web application. It follows standard **Software Testing Life Cycle (STLC)** practices, including test planning, test case design, execution, defect reporting, and test summary reporting.

**Application Under Test:** AgileWay Travel  
**Application URL:** https://travel.agileway.net/login  
**Testing Type:** Manual / Functional Testing  
**Project Duration:** January 2026  
**Tester:** Pragati Nangare  

---

## Objectives
- Perform functional and validation testing of a flight booking system  
- Identify defects related to business logic and input validation  
- Create detailed test cases and professional bug reports  
- Demonstrate real-world manual testing and QA documentation skills  

---

## Testing Scope

### Modules Tested
- Login  
- Flight Selection  
- Passenger Details  
- Payment  

---

## Testing Types Performed
- Functional Testing  
- Validation Testing  
- Negative Testing  
- Boundary Value Testing  
- UI Testing  

---

## Test Statistics

| Metric | Count |
|------|------|
| Total Test Cases | 38 |
| Test Cases Executed | 38 |
| Bugs Identified | 13 |
| Modules Tested | 4 |
| Modules with Bugs | 3 |
| Test Coverage | 100% |

---

## Bug Summary

### Bugs by Module

| Module | Bugs Found |
|------|-----------|
| Flight Selection | 5 |
| Passenger Details | 4 |
| Payment | 4 |
| **Total** | **13** |

---

### Bugs by Severity

| Severity | Count |
|---------|------|
| Critical | 3 |
| High | 4 |
| Medium | 6 |
| Low | 0 |

---

### Bugs by Priority

| Priority | Count |
|---------|------|
| P1 | 7 |
| P2 | 6 |
| P3 | 0 |

---

## Key Defects Identified
- Flight search proceeds without selecting mandatory fields (origin, destination, departure date)
- Return date accepted earlier than departure date
- Passenger name fields accept numeric and special characters
- Payment proceeds with empty or invalid card numbers
- Card number field lacks length and format validation

---

## Test Artifacts

### Test Cases
**File:** `Test_Cases_Complete.xlsx`
- 38 detailed manual test cases
- Step-by-step execution flow
- Test data and expected results
- Priority classification

### Bug Report
**File:** `Bug_Report_AgileWay_Travel.pdf`
- 13 documented defects
- Clear reproduction steps
- Expected vs actual results
- Severity and priority mapping
- Evidence attached (screenshots and videos)

---

## Tools & Environment
- Test Management Tool: Jira  
- Bug Tracking Tool: Jira  
- Documentation: Microsoft Excel, Word  
- Browser: Google Chrome  
- Operating System: Windows 11  

---

## Testing Approach
1. Requirement analysis and understanding application flow  
2. Identification of test scenarios  
3. Test case design and review  
4. Manual execution of test cases  
5. Defect identification and reporting  
6. Test summary and quality recommendations  

---

## Quality Observations
- Missing mandatory field validations across modules  
- Business logic gaps in date selection and flight search  
- Critical validation issues in the payment module  
- Lack of input sanitization for text fields  

---

## Recommendations
- Implement client-side and server-side input validation  
- Add logical checks for flight date combinations  
- Strengthen payment validation rules  
- Perform regression testing after bug fixes  

---

## Skills Demonstrated
- Manual Testing  
- Functional Testing  
- Test Case Design  
- Bug Reporting  
- STLC  
- Defect Life Cycle  
- Validation Testing  
- Negative Testing  
- Test Documentation  

---


## Notes
- This project is created for learning and skill demonstration purposes  
- All test data used is dummy data  
- No real transactions were performed  


