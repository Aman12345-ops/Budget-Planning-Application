# Test Cases — Budget Planning Application

## 1. Document Information

| Field | Details |
|---|---|
| Project | Budget Planning Application |
| Document | Test Cases |
| Version | 1.0 |
| Author | Ansh Pandey |
| Year | 2026 |
| Application Type | Client-Side Web Application |
| Storage | Browser LocalStorage |

---

## 2. Purpose

This document defines the practical test cases used to verify the functional correctness, usability, data persistence, validation, calculations, and responsiveness of the Budget Planning Application.

The application is tested against its major functional modules, including:

- Dashboard
- Income management
- Expense management
- Transaction editing
- Transaction deletion
- Search and filtering
- Monthly budget
- Savings goal
- Category analysis
- LocalStorage persistence
- CSV export
- Reset demo data
- Responsive interface

---

## 3. Test Environment

### Hardware

- Laptop/Desktop computer
- Minimum 4 GB RAM
- Keyboard and mouse/touchpad
- Mobile device for responsive testing

### Software

- Windows/Linux/macOS
- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Visual Studio Code
- Modern JavaScript-enabled browser

---

# 4. Test Cases

## 4.1 Application Initialization

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-001 | Open application | Open `src/index.html` in browser | Application loads successfully | Pass |
| TC-002 | Check dashboard | Open application and observe dashboard | Dashboard cards and sections are displayed | Pass |
| TC-003 | Load saved data | Refresh application after storing data | Previously saved data is loaded | Pass |
| TC-004 | Empty storage handling | Clear LocalStorage and reopen application | Application initializes without crashing | Pass |

---

# 5. Income Management

## 5.1 Add Income

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-005 | Add valid income | Enter description, category, amount and date; select Income; submit | Income transaction is added | Pass |
| TC-006 | Verify income total | Add an income transaction | Total income increases correctly | Pass |
| TC-007 | Missing description | Leave description empty and submit | Validation message is displayed | Pass |
| TC-008 | Missing amount | Leave amount empty and submit | Validation message is displayed | Pass |
| TC-009 | Invalid amount | Enter zero/negative amount | Invalid value is rejected | Pass |
| TC-010 | Missing date | Leave date empty and submit | Validation message is displayed | Pass |

---

# 6. Expense Management

## 6.1 Add Expense

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-011 | Add valid expense | Enter valid expense information and submit | Expense is added successfully | Pass |
| TC-012 | Verify expense total | Add an expense | Total expense increases correctly | Pass |
| TC-013 | Missing description | Leave description empty | Validation message is displayed | Pass |
| TC-014 | Missing category | Leave category empty | Validation message is displayed | Pass |
| TC-015 | Invalid expense amount | Enter negative/zero amount | Expense is rejected | Pass |
| TC-016 | Verify transaction table | Add expense | New expense appears in transaction list | Pass |

---

# 7. Transaction Management

## 7.1 Edit Transaction

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-017 | Edit transaction | Select an existing transaction and click Edit | Transaction data is loaded into the form | Pass |
| TC-018 | Update description | Change transaction description and save | Updated description is displayed | Pass |
| TC-019 | Update amount | Change transaction amount and save | Amount and totals are recalculated | Pass |
| TC-020 | Update category | Change category and save | New category is displayed | Pass |

## 7.2 Delete Transaction

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-021 | Delete transaction | Click Delete for an existing transaction | Transaction is removed | Pass |
| TC-022 | Verify total after deletion | Delete an expense | Total expense is reduced correctly | Pass |
| TC-023 | Verify income after deletion | Delete an income | Total income is reduced correctly | Pass |

---

# 8. Dashboard Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-024 | Total income calculation | Add multiple incomes | Dashboard shows correct total income | Pass |
| TC-025 | Total expense calculation | Add multiple expenses | Dashboard shows correct total expense | Pass |
| TC-026 | Balance calculation | Add income and expense | Balance = Income − Expense | Pass |
| TC-027 | Transaction count | Add multiple transactions | Correct number of transactions is displayed | Pass |
| TC-028 | Dashboard refresh | Modify transaction data | Dashboard values update automatically | Pass |

---

# 9. Budget Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-029 | Set monthly budget | Enter valid budget and save | Budget is stored successfully | Pass |
| TC-030 | Display budget | Set a budget | Dashboard displays budget amount | Pass |
| TC-031 | Budget usage | Add expenses after setting budget | Budget usage is calculated correctly | Pass |
| TC-032 | Budget percentage | Add expenses within budget | Correct percentage is displayed | Pass |
| TC-033 | Budget exceeded | Add expenses greater than budget | Application indicates budget overuse | Pass |
| TC-034 | Budget persistence | Set budget and refresh page | Budget remains available | Pass |

### Budget Calculation

The budget usage percentage is calculated as:

```text
Budget Usage (%) = (Total Expenses / Monthly Budget) × 100
```

Example:

```text
Total Expenses = ₹7,500
Monthly Budget = ₹15,000

Budget Usage = (7,500 / 15,000) × 100
             = 50%
```

---

# 10. Savings Goal Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-035 | Set savings goal | Enter valid savings goal | Goal is saved successfully | Pass |
| TC-036 | Display savings goal | Set savings goal | Goal appears on dashboard | Pass |
| TC-037 | Savings progress | Add income and expenses | Savings/progress value updates | Pass |
| TC-038 | Savings persistence | Set goal and refresh page | Goal remains stored | Pass |

### Savings Calculation

The application calculates available savings as:

```text
Savings = Total Income − Total Expenses
```

Savings progress can be represented as:

```text
Savings Progress (%) =
(Savings / Savings Goal) × 100
```

---

# 11. Search Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-039 | Search by description | Enter an existing transaction description | Matching transaction is displayed | Pass |
| TC-040 | Search by category | Enter a category name | Matching transactions are displayed | Pass |
| TC-041 | Search unavailable data | Enter text that does not exist | No matching transaction is displayed | Pass |

---

# 12. Filter Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-042 | Filter income | Select Income filter | Only income transactions are displayed | Pass |
| TC-043 | Filter expense | Select Expense filter | Only expense transactions are displayed | Pass |
| TC-044 | Clear filter | Select All/clear filter | All transactions are displayed | Pass |

---

# 13. Category Analysis Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-045 | Category analysis | Add expenses from different categories | Category-wise analysis is generated | Pass |
| TC-046 | Verify category amount | Add multiple expenses in same category | Category total is calculated correctly | Pass |
| TC-047 | Update analysis | Add/delete an expense | Category analysis updates automatically | Pass |

---

# 14. CSV Export Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-048 | Export transactions | Click Export CSV | CSV file is generated/downloaded | Pass |
| TC-049 | Verify CSV headers | Open exported CSV | Required transaction columns are present | Pass |
| TC-050 | Verify CSV records | Compare CSV with application transactions | Exported records match stored transactions | Pass |

Expected CSV structure:

```text
ID,Type,Description,Category,Amount,Date
1,Income,Salary,Salary,30000,2026-10-01
2,Expense,Groceries,Food,3500,2026-10-02
```

---

# 15. LocalStorage Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-051 | Store transaction | Add transaction and inspect LocalStorage | Transaction data is stored | Pass |
| TC-052 | Refresh persistence | Add transaction and refresh page | Transaction remains available | Pass |
| TC-053 | Update persistence | Edit transaction and refresh | Updated data remains available | Pass |
| TC-054 | Delete persistence | Delete transaction and refresh | Deleted transaction does not return | Pass |

Expected LocalStorage key:

```text
budgetPlanningApplication
```

---

# 16. Reset Demo Data Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-055 | Reset demo data | Click Reset Demo Data | Demo dataset is restored | Pass |
| TC-056 | Verify reset transactions | Reset application | Default transactions are displayed | Pass |
| TC-057 | Verify reset budget | Reset application | Default budget is restored | Pass |
| TC-058 | Verify reset savings goal | Reset application | Default savings goal is restored | Pass |

---

# 17. Responsive UI Testing

| ID | Test Case | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-059 | Desktop view | Open application on desktop | Layout displays correctly | Pass |
| TC-060 | Tablet view | Resize browser to tablet width | Components remain usable | Pass |
| TC-061 | Mobile view | Resize browser to mobile width | Layout adapts without horizontal overflow | Pass |
| TC-062 | Mobile transaction form | Open form on mobile | Inputs and buttons remain accessible | Pass |

---

# 18. Browser Compatibility Testing

| Browser | Expected Result | Status |
|---|---|---|
| Google Chrome | Application works correctly | Pass |
| Microsoft Edge | Application works correctly | Pass |
| Mozilla Firefox | Application works correctly | Pass |

---

# 19. Validation and Error Handling

The application should prevent invalid financial records from being stored.

The following conditions are validated:

1. Required fields must not be empty.
2. Transaction amount must be greater than zero.
3. Transaction type must be valid.
4. Category should be selected where required.
5. Date should contain a valid value.
6. Budget should be a valid positive amount.
7. Savings goal should be a valid positive amount.
8. Invalid operations should not corrupt stored data.
9. The application should continue functioning after validation errors.

---

# 20. Test Summary

| Testing Area | Test Cases | Result |
|---|---:|---|
| Application Initialization | 4 | Pass |
| Income Management | 6 | Pass |
| Expense Management | 6 | Pass |
| Transaction Management | 7 | Pass |
| Dashboard | 5 | Pass |
| Budget | 6 | Pass |
| Savings Goal | 4 | Pass |
| Search | 3 | Pass |
| Filter | 3 | Pass |
| Category Analysis | 3 | Pass |
| CSV Export | 3 | Pass |
| LocalStorage | 4 | Pass |
| Reset Demo Data | 4 | Pass |
| Responsive UI | 4 | Pass |
| Browser Compatibility | 3 | Pass |
| **Total** | **62** | **Pass** |

---

# 21. Acceptance Criteria

The Budget Planning Application is considered functionally acceptable when:

- Users can add income and expense transactions.
- Users can edit and delete transactions.
- Dashboard totals are calculated correctly.
- Monthly budget can be configured and monitored.
- Savings goals can be configured and monitored.
- Transactions can be searched and filtered.
- Category-wise expense analysis is available.
- Data persists using browser LocalStorage.
- Transactions can be exported as CSV.
- Demo data can be reset.
- Required input validation works correctly.
- The interface remains usable on desktop, tablet, and mobile screens.
- No critical functional defects remain.

---

# 22. Conclusion

The test cases defined in this document provide systematic verification of the Budget Planning Application. Functional, validation, persistence, calculation, export, responsive interface, and browser compatibility scenarios are covered.

The testing process confirms that the application satisfies its core functional requirements and provides a reliable client-side solution for basic personal budget and expense management.
