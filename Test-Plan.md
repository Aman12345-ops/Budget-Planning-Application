# Test Plan — Budget Planning Application

**Project Name:** Budget Planning Application  
**Document:** Software Testing and Test Plan  
**Author:** Ansh Pandey  
**Year:** 2026  
**Technology:** HTML5, CSS3, JavaScript ES6, Browser LocalStorage  
**Version:** 1.0  
**Status:** Academic Project

---

# 1. Introduction

Software testing is the process of evaluating a software system to determine whether it satisfies its specified requirements and behaves as expected.

The Budget Planning Application requires testing of its financial transaction management, budget management, savings tracking, search and filtering, data persistence, calculations, export functionality, and user interface.

This Test Plan defines the testing approach, test objectives, test environment, test cases, expected results, and acceptance criteria for the application.

---

# 2. Purpose

The purpose of this Test Plan is to:

- Verify that the application satisfies its functional requirements.
- Identify defects before project submission.
- Verify financial calculations.
- Test transaction CRUD operations.
- Verify data persistence.
- Test input validation.
- Verify budget functionality.
- Verify savings goal functionality.
- Test search and filtering.
- Test CSV export.
- Verify responsive user interface behavior.
- Provide documented evidence of software quality.

---

# 3. Testing Objectives

The main testing objectives are:

1. Verify that all major features work correctly.
2. Verify that valid data is accepted.
3. Verify that invalid data is rejected.
4. Verify that transactions are correctly created.
5. Verify that transactions can be edited and deleted.
6. Verify that financial calculations are accurate.
7. Verify that budget calculations are correct.
8. Verify that savings calculations are correct.
9. Verify that LocalStorage persistence works.
10. Verify that search and filter functions return correct results.
11. Verify that CSV export works correctly.
12. Verify that reset functionality works.
13. Verify that the application works across different screen sizes.

---

# 4. Scope of Testing

## 4.1 In Scope

The following features are included:

- Application initialization
- Dashboard
- Income management
- Expense management
- Transaction creation
- Transaction editing
- Transaction deletion
- Search
- Filtering
- Monthly budget
- Budget monitoring
- Savings goal
- Savings progress
- Category analysis
- LocalStorage
- CSV export
- Reset demo data
- Input validation
- Error handling
- Responsive interface

## 4.2 Out of Scope

The following are not part of the current implementation:

- User authentication
- Multi-user management
- Online banking integration
- Payment processing
- Cloud database
- Server-side API testing
- Real-time synchronization
- Bank account integration

---

# 5. Testing Strategy

The project uses multiple testing approaches.

| Testing Type | Purpose |
|---|---|
| Functional Testing | Verify application features |
| Unit-Level Logic Testing | Verify individual calculations and functions |
| Integration Testing | Verify interaction between modules |
| System Testing | Verify complete application behavior |
| Validation Testing | Verify invalid input handling |
| UI Testing | Verify interface behavior |
| Responsive Testing | Verify different screen sizes |
| Regression Testing | Ensure changes do not break existing features |
| Data Persistence Testing | Verify LocalStorage behavior |
| User Acceptance Testing | Verify project meets user expectations |

---

# 6. Test Environment

## Hardware

Recommended testing environment:

- Computer/Laptop
- Minimum 4 GB RAM
- Keyboard and mouse
- Display supporting desktop resolution

## Software

- Windows / Linux / macOS
- Modern web browser
- Visual Studio Code
- Git
- GitHub

## Supported Browsers

Testing can be performed using:

- Google Chrome
- Microsoft Edge
- Mozilla Firefox

---

# 7. Test Data

The following sample data can be used during testing.

### Income

```text
Description: Salary
Category: Salary
Amount: ₹30,000
Date: 2026-10-01
Type: Income
```

### Expense

```text
Description: Groceries
Category: Food
Amount: ₹3,500
Date: 2026-10-02
Type: Expense
```

### Expense

```text
Description: Bus Pass
Category: Transport
Amount: ₹1,200
Date: 2026-10-03
Type: Expense
```

### Budget

```text
Monthly Budget: ₹15,000
```

### Savings Goal

```text
Savings Goal: ₹10,000
```

---

# 8. Test Case Format

Each test case contains:

- Test Case ID
- Module
- Test Scenario
- Preconditions
- Test Steps
- Test Data
- Expected Result
- Actual Result
- Status

---

# 9. Application Initialization Test Cases

## TC-001 — Application Loading

**Module:** Application Initialization

**Scenario:** Verify that the application loads successfully.

**Precondition:** Application files are available.

**Steps:**

1. Open `index.html`.
2. Wait for the page to load.

**Expected Result:**

The dashboard should load without errors.

**Actual Result:** To be recorded during execution.

**Status:** Pass / Fail

---

## TC-002 — LocalStorage Data Loading

**Module:** Data Persistence

**Scenario:** Verify that saved data is loaded when the application starts.

**Steps:**

1. Add a transaction.
2. Refresh the browser.
3. Check the transaction list.

**Expected Result:**

The previously stored transaction should remain available.

**Status:** Pass / Fail

---

## TC-003 — Initial Demo Data

**Module:** Application Initialization

**Scenario:** Verify that default/demo data is loaded when no saved data exists.

**Steps:**

1. Clear application LocalStorage.
2. Reload the application.

**Expected Result:**

The application should load its predefined demonstration/default state.

**Status:** Pass / Fail

---

# 10. Dashboard Test Cases

## TC-004 — Dashboard Display

**Scenario:** Verify that dashboard cards are displayed.

**Steps:**

1. Open the application.
2. Observe the dashboard.

**Expected Result:**

Dashboard information such as income, expenses, balance, budget, and savings should be displayed.

**Status:** Pass / Fail

---

## TC-005 — Total Income Calculation

**Scenario:** Verify total income calculation.

**Test Data:**

```text
Income = ₹30,000
```

**Expected Result:**

Total income should display ₹30,000.

**Status:** Pass / Fail

---

## TC-006 — Total Expense Calculation

**Scenario:** Verify total expense calculation.

**Test Data:**

```text
Groceries = ₹3,500
Bus Pass = ₹1,200
```

**Expected Result:**

Total expense should equal:

```text
₹3,500 + ₹1,200 = ₹4,700
```

**Status:** Pass / Fail

---

## TC-007 — Balance Calculation

**Scenario:** Verify current balance.

**Test Data:**

```text
Income = ₹30,000
Expense = ₹4,700
```

**Expected Result:**

```text
Balance = ₹30,000 - ₹4,700
        = ₹25,300
```

**Status:** Pass / Fail

---

# 11. Add Income Test Cases

## TC-008 — Add Valid Income

**Scenario:** Add a valid income transaction.

**Steps:**

1. Open transaction form.
2. Select Income.
3. Enter description.
4. Select category.
5. Enter amount.
6. Select date.
7. Submit.

**Expected Result:**

The income should appear in the transaction list and dashboard totals should update.

**Status:** Pass / Fail

---

## TC-009 — Missing Income Description

**Scenario:** Submit income without a description.

**Expected Result:**

The system should display a validation message and should not save the transaction.

**Status:** Pass / Fail

---

## TC-010 — Invalid Income Amount

**Scenario:** Enter an invalid amount.

**Test Data:**

```text
Amount = -500
```

**Expected Result:**

The system should reject the invalid amount.

**Status:** Pass / Fail

---

# 12. Add Expense Test Cases

## TC-011 — Add Valid Expense

**Scenario:** Add a valid expense transaction.

**Expected Result:**

The expense should be saved and total expenses should increase.

**Status:** Pass / Fail

---

## TC-012 — Missing Expense Category

**Scenario:** Submit an expense without selecting a category.

**Expected Result:**

The application should display an appropriate validation message.

**Status:** Pass / Fail

---

## TC-013 — Zero Expense Amount

**Scenario:** Enter zero as expense amount.

**Test Data:**

```text
Amount = 0
```

**Expected Result:**

The application should reject the transaction.

**Status:** Pass / Fail

---

# 13. Edit Transaction Test Cases

## TC-014 — Edit Existing Transaction

**Scenario:** Modify an existing transaction.

**Steps:**

1. Select an existing transaction.
2. Click Edit.
3. Modify the amount.
4. Save changes.

**Expected Result:**

The transaction should contain the updated amount.

**Status:** Pass / Fail

---

## TC-015 — Edit With Invalid Amount

**Scenario:** Change transaction amount to an invalid value.

**Expected Result:**

The application should reject the update.

**Status:** Pass / Fail

---

# 14. Delete Transaction Test Cases

## TC-016 — Delete Existing Transaction

**Scenario:** Delete a transaction.

**Steps:**

1. Select a transaction.
2. Click Delete.

**Expected Result:**

The transaction should disappear from the transaction list and financial totals should be recalculated.

**Status:** Pass / Fail

---

## TC-017 — Delete Persistence

**Scenario:** Verify deletion persists after refresh.

**Steps:**

1. Delete a transaction.
2. Refresh the browser.

**Expected Result:**

The deleted transaction should not return.

**Status:** Pass / Fail

---

# 15. Search Test Cases

## TC-018 — Search Existing Transaction

**Scenario:** Search for an existing transaction.

**Test Data:**

```text
Search = Groceries
```

**Expected Result:**

The Groceries transaction should be displayed.

**Status:** Pass / Fail

---

## TC-019 — Search Non-existing Transaction

**Scenario:** Search for a transaction that does not exist.

**Test Data:**

```text
Search = Laptop
```

**Expected Result:**

No matching transaction should be displayed.

**Status:** Pass / Fail

---

# 16. Filter Test Cases

## TC-020 — Filter Income

**Scenario:** Filter transaction list by Income.

**Expected Result:**

Only income transactions should be displayed.

**Status:** Pass / Fail

---

## TC-021 — Filter Expense

**Scenario:** Filter transaction list by Expense.

**Expected Result:**

Only expense transactions should be displayed.

**Status:** Pass / Fail

---

## TC-022 — Category Filter

**Scenario:** Filter transactions using a category.

**Expected Result:**

Only transactions belonging to the selected category should be displayed.

**Status:** Pass / Fail

---

# 17. Budget Test Cases

## TC-023 — Set Valid Budget

**Scenario:** Set monthly budget.

**Test Data:**

```text
₹15,000
```

**Expected Result:**

The budget should be saved successfully.

**Status:** Pass / Fail

---

## TC-024 — Invalid Budget

**Scenario:** Enter an invalid budget.

**Test Data:**

```text
₹0
```

**Expected Result:**

The application should reject the value.

**Status:** Pass / Fail

---

## TC-025 — Budget Usage Calculation

**Scenario:** Verify budget usage.

**Test Data:**

```text
Budget = ₹15,000
Expenses = ₹4,700
```

**Expected Result:**

The application should calculate the budget usage correctly according to its implementation logic.

**Status:** Pass / Fail

---

## TC-026 — Budget Exceeded

**Scenario:** Expenses exceed the configured budget.

**Steps:**

1. Set budget to ₹5,000.
2. Add expenses greater than ₹5,000.

**Expected Result:**

The application should indicate that the budget has been exceeded.

**Status:** Pass / Fail

---

# 18. Savings Goal Test Cases

## TC-027 — Set Savings Goal

**Scenario:** Set a valid savings goal.

**Test Data:**

```text
₹10,000
```

**Expected Result:**

The savings goal should be saved.

**Status:** Pass / Fail

---

## TC-028 — Invalid Savings Goal

**Scenario:** Enter an invalid savings goal.

**Test Data:**

```text
₹0
```

**Expected Result:**

The application should reject the value.

**Status:** Pass / Fail

---

## TC-029 — Savings Progress

**Scenario:** Verify savings progress calculation.

**Steps:**

1. Set a savings goal.
2. Maintain income and expense records.
3. Observe savings progress.

**Expected Result:**

The application should calculate and display savings progress correctly.

**Status:** Pass / Fail

---

# 19. Category Analysis Test Cases

## TC-030 — Category Analysis

**Scenario:** Verify category-wise expense analysis.

**Test Data:**

```text
Food = ₹3,500
Transport = ₹1,200
```

**Expected Result:**

The analysis should show the corresponding category totals.

**Status:** Pass / Fail

---

## TC-031 — Multiple Transactions Same Category

**Scenario:** Verify that transactions from the same category are combined.

**Test Data:**

```text
Food = ₹3,500
Food = ₹800
```

**Expected Result:**

Food category total should be:

```text
₹4,300
```

**Status:** Pass / Fail

---

# 20. CSV Export Test Cases

## TC-032 — Export Transactions

**Scenario:** Export transaction data.

**Steps:**

1. Add at least one transaction.
2. Click Export CSV.

**Expected Result:**

A CSV file should be generated/downloaded.

**Status:** Pass / Fail

---

## TC-033 — Verify CSV Contents

**Scenario:** Verify exported data.

**Expected Result:**

The CSV should contain transaction fields such as:

```text
ID
Type
Description
Category
Amount
Date
```

**Status:** Pass / Fail

---

# 21. Reset Demo Data Test Cases

## TC-034 — Reset Application Data

**Scenario:** Reset the application.

**Steps:**

1. Add or modify transactions.
2. Click Reset Demo Data.
3. Confirm reset.

**Expected Result:**

The application should return to its predefined demonstration state.

**Status:** Pass / Fail

---

## TC-035 — Cancel Reset

**Scenario:** Cancel reset operation if confirmation is available.

**Expected Result:**

Existing application data should remain unchanged.

**Status:** Pass / Fail

---

# 22. LocalStorage Test Cases

## TC-036 — Save Data

**Scenario:** Verify that data is stored in LocalStorage.

**Steps:**

1. Add a transaction.
2. Open browser developer tools.
3. Check LocalStorage.

**Expected Result:**

Application data should be present under the configured application key.

**Status:** Pass / Fail

---

## TC-037 — Refresh Persistence

**Scenario:** Verify data after browser refresh.

**Expected Result:**

Saved transactions and settings should remain available.

**Status:** Pass / Fail

---

## TC-038 — Data Update

**Scenario:** Verify LocalStorage after editing data.

**Expected Result:**

LocalStorage should contain the updated transaction information.

**Status:** Pass / Fail

---

# 23. Responsive UI Test Cases

## TC-039 — Desktop View

**Scenario:** Test application on desktop screen.

**Expected Result:**

The layout should be properly aligned and readable.

**Status:** Pass / Fail

---

## TC-040 — Tablet View

**Scenario:** Test application on tablet-sized screen.

**Expected Result:**

The interface should adapt without major layout issues.

**Status:** Pass / Fail

---

## TC-041 — Mobile View

**Scenario:** Test application on mobile-sized screen.

**Expected Result:**

The application should remain usable with responsive layout.

**Status:** Pass / Fail

---

# 24. Browser Compatibility Test Cases

## TC-042 — Google Chrome

**Expected Result:**

Application should function correctly.

**Status:** Pass / Fail

---

## TC-043 — Microsoft Edge

**Expected Result:**

Application should function correctly.

**Status:** Pass / Fail

---

## TC-044 — Mozilla Firefox

**Expected Result:**

Application should function correctly.

**Status:** Pass / Fail

---

# 25. Integration Test Cases

## TC-045 — Transaction and Dashboard Integration

**Scenario:** Add an expense and verify dashboard update.

**Expected Result:**

Transaction list and dashboard totals should update consistently.

**Status:** Pass / Fail

---

## TC-046 — Transaction and Budget Integration

**Scenario:** Add an expense and verify budget usage.

**Expected Result:**

Budget utilization should update according to the new expense.

**Status:** Pass / Fail

---

## TC-047 — Transaction and Category Analysis Integration

**Scenario:** Add an expense under a category.

**Expected Result:**

The category analysis should reflect the new expense.

**Status:** Pass / Fail

---

## TC-048 — Transaction and Savings Integration

**Scenario:** Change financial transactions and observe savings information.

**Expected Result:**

Savings information should update according to the application's calculation logic.

**Status:** Pass / Fail

---

# 26. Regression Testing

Regression testing should be performed after major changes to the application.

After modifying `script.js`, `style.css`, or `index.html`, the following features should be re-tested:

- Dashboard
- Add income
- Add expense
- Edit
- Delete
- Search
- Filter
- Budget
- Savings
- Category analysis
- CSV export
- LocalStorage
- Reset

The objective is to ensure that a new code change does not break previously working functionality.

---

# 27. Performance Testing

Basic performance testing should verify:

- Fast initial page loading.
- Smooth transaction operations.
- Quick dashboard updates.
- Responsive search and filtering.
- Efficient rendering of transaction records.
- No unnecessary repeated calculations.

For the expected small academic dataset, the application should respond quickly under normal browser conditions.

---

# 28. Usability Testing

The following usability aspects should be evaluated:

- Clear navigation.
- Understandable labels.
- Readable financial values.
- Simple transaction entry.
- Visible error messages.
- Easy-to-use buttons.
- Responsive design.
- Clear dashboard information.

---

# 29. Security Testing

Since the application is client-side, security testing focuses on:

- Input validation.
- Preventing invalid data storage.
- Avoiding sensitive information in LocalStorage.
- Safe handling of user input.
- Avoiding accidental data corruption.

A future backend implementation would require additional security testing.

---

# 30. Defect Severity

| Severity | Description |
|---|---|
| Critical | Application cannot function |
| High | Major feature is unusable |
| Medium | Important feature has incorrect behavior |
| Low | Minor issue with limited impact |
| Cosmetic | Visual/UI issue |

---

# 31. Defect Reporting Format

When a defect is identified, it can be recorded using:

```text
Defect ID:
Test Case ID:
Date:
Module:
Description:
Steps to Reproduce:
Expected Result:
Actual Result:
Severity:
Priority:
Status:
Resolution:
```

---

# 32. Test Execution Summary

The final test execution summary can be maintained in the following format:

| Metric | Value |
|---|---:|
| Total Test Cases | 48 |
| Passed | To be recorded |
| Failed | To be recorded |
| Blocked | To be recorded |
| Not Executed | To be recorded |
| Pass Percentage | To be calculated |

### Pass Percentage

```text
Pass Percentage
=
Passed Test Cases / Executed Test Cases × 100
```

---

# 33. Acceptance Criteria

The application can be considered ready for academic submission when:

1. Core application features work correctly.
2. Income can be added successfully.
3. Expenses can be added successfully.
4. Transactions can be edited.
5. Transactions can be deleted.
6. Dashboard calculations are correct.
7. Budget functionality works correctly.
8. Savings goal functionality works correctly.
9. Search works correctly.
10. Filtering works correctly.
11. Category analysis works correctly.
12. CSV export works correctly.
13. LocalStorage persistence works correctly.
14. Invalid inputs are handled appropriately.
15. Reset functionality works correctly.
16. Responsive layout is usable.
17. No critical or high-severity unresolved defects remain.

---

# 34. Test Completion Criteria

Testing can be considered complete when:

- All planned test cases have been executed.
- Critical functionality has been verified.
- Major defects have been resolved.
- Regression testing has been performed.
- Data persistence has been verified.
- Responsive behavior has been checked.
- Acceptance criteria have been satisfied.

---

# 35. Traceability

The test cases provide coverage for the major functional areas:

| Requirement Area | Test Cases |
|---|---|
| Dashboard | TC-004 to TC-007 |
| Income | TC-008 to TC-010 |
| Expense | TC-011 to TC-013 |
| Edit | TC-014 to TC-015 |
| Delete | TC-016 to TC-017 |
| Search | TC-018 to TC-019 |
| Filter | TC-020 to TC-022 |
| Budget | TC-023 to TC-026 |
| Savings | TC-027 to TC-029 |
| Category Analysis | TC-030 to TC-031 |
| Export | TC-032 to TC-033 |
| Reset | TC-034 to TC-035 |
| LocalStorage | TC-036 to TC-038 |
| Responsive UI | TC-039 to TC-041 |
| Browser Compatibility | TC-042 to TC-044 |
| Integration | TC-045 to TC-048 |

---

# 36. Testing Checklist

- [x] Functional testing planned.
- [x] Transaction CRUD testing planned.
- [x] Dashboard testing planned.
- [x] Budget testing planned.
- [x] Savings testing planned.
- [x] Search testing planned.
- [x] Filter testing planned.
- [x] Category analysis testing planned.
- [x] CSV export testing planned.
- [x] LocalStorage testing planned.
- [x] Responsive testing planned.
- [x] Browser testing planned.
- [x] Integration testing planned.
- [x] Regression testing planned.
- [x] Acceptance criteria defined.
- [x] Defect reporting format defined.

---

# 37. Conclusion

The Test Plan provides a structured approach for validating the Budget Planning Application.

It covers functional behavior, financial calculations, data persistence, validation, user interface behavior, responsive design, browser compatibility, integration, and regression testing.

The defined test cases provide measurable criteria for determining whether the application meets its functional requirements and is suitable for academic submission.

---

## Project Information

**Project:** Budget Planning Application  
**Document:** Software Testing and Test Plan  
**Author:** Ansh Pandey  
**Year:** 2026  
**Version:** 1.0  
**Status:** Academic Project
