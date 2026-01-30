# Defect Report – To-Do List Application

This document summarizes the key functional defects identified during
manual testing of the To-Do List web application.
Defects were logged and tracked using Trello.

---

## BUG-001: Item count does not increment correctly on adding a to-do
**Severity:** High  

**Steps to Reproduce:**
1. Open the To-Do List application
2. Add a new to-do item using the input field
3. Observe the item count displayed

**Expected Result:**
Item count should increase by 1 when a new to-do is added

**Actual Result:**
Item count does not update correctly

**Impact:**
User receives incorrect information about active to-do items

---

## BUG-002: Incorrect “X items left” count displayed
**Severity:** High  

**Steps to Reproduce:**
1. Add multiple to-do items
2. Mark one or more items as completed
3. Observe the “X items left” count

**Expected Result:**
Displayed count should match the number of active to-do items

**Actual Result:**
Displayed count does not reflect the correct number of active items

**Impact:**
Misleading information is shown to the user

---

## BUG-003: Item count does not show zero when all to-dos are completed
**Severity:** High  

**Steps to Reproduce:**
1. Add multiple to-do items
2. Mark all items as completed
3. Observe the item count

**Expected Result:**
Item count should display zero when all items are completed

**Actual Result:**
Item count still shows remaining items

**Impact:**
Core functionality behaves incorrectly, affecting user trust

---

## Note
All listed defects impact core application functionality and user-facing data,therefore they are classified as High severity.
