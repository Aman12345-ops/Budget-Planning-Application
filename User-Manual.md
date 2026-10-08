# User Manual — Budget Planning Application

**Project Name:** Budget Planning Application  
**Document:** User Manual  
**Author:** Ansh Pandey  
**Year:** 2026  
**Technology:** HTML5, CSS3, JavaScript ES6, Browser LocalStorage  
**Version:** 1.0  
**Status:** Academic Project

---

# 1. Introduction

The Budget Planning Application is a browser-based financial management application designed to help users manage their income, expenses, monthly budget, and savings goals.

The application provides a simple dashboard where users can record financial transactions, monitor spending, analyze expenses, and track savings progress.

The current application works entirely on the client side and uses Browser LocalStorage for persistent data storage.

---

# 2. Purpose of This Manual

This User Manual explains how to:

- Open the application.
- Understand the dashboard.
- Add income.
- Add expenses.
- Edit transactions.
- Delete transactions.
- Search transactions.
- Filter transactions.
- Set a monthly budget.
- Monitor budget usage.
- Set a savings goal.
- Monitor savings progress.
- View category analysis.
- Export transactions to CSV.
- Reset demo data.
- Understand data persistence.

---

# 3. System Requirements

## 3.1 Hardware Requirements

A basic computer or laptop is sufficient.

Recommended:

- 4 GB RAM or more.
- Modern processor.
- Keyboard and mouse.
- Display with standard desktop resolution.

## 3.2 Software Requirements

The application requires:

- Windows, Linux, or macOS.
- A modern web browser.
- Google Chrome, Microsoft Edge, or Mozilla Firefox.

No server installation is required for the current version.

---

# 4. Project Structure

The project contains the following major directories:

```text
Budget-Planning-Application/
│
├── README.md
├── SRS.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── 01-System-Design.md
│   ├── 02-Use-Case-Diagram.md
│   ├── 03-DFD.md
│   ├── 04-ER-Diagram.md
│   ├── 05-Flowchart.md
│   ├── 06-Database-Design.md
│   ├── 07-Test-Plan.md
│   └── 08-User-Manual.md
│
├── src/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── tests/
│   └── test-cases.md
│
└── screenshots/
```

---

# 5. Opening the Application

The current application does not require Node.js or a backend server.

## Method 1 — Open Directly

Navigate to:

```text
src/index.html
```

Double-click the file or open it in a supported browser.

---

## Method 2 — Using Visual Studio Code

1. Open Visual Studio Code.
2. Select **File → Open Folder**.
3. Select the `Budget-Planning-Application` folder.
4. Open:

```text
src/index.html
```

5. Open the file in a browser.

If Live Server is installed, the application can also be launched using the **Open with Live Server** option.

---

# 6. Dashboard

After opening the application, the user is presented with the main dashboard.

The dashboard provides a summary of financial information.

Typical dashboard information includes:

- Total Income
- Total Expenses
- Current Balance
- Monthly Budget
- Budget Usage
- Savings Goal
- Savings Progress

The dashboard automatically updates when transaction or financial settings change.

---

# 7. Understanding Income

Income represents money received by the user.

Examples:

- Salary
- Freelancing
- Scholarship
- Business income
- Other income

Income transactions increase the total income and affect the overall balance.

---

# 8. Adding an Income Transaction

To add income:

### Step 1

Open the transaction form.

### Step 2

Select:

```text
Income
```

### Step 3

Enter the transaction description.

Example:

```text
Salary
```

### Step 4

Select an appropriate category.

Example:

```text
Salary
```

### Step 5

Enter the amount.

Example:

```text
30000
```

### Step 6

Select the transaction date.

### Step 7

Submit the form.

The transaction should appear in the transaction list.

The dashboard will automatically recalculate the financial summary.

---

# 9. Adding an Expense Transaction

To add an expense:

### Step 1

Open the transaction form.

### Step 2

Select:

```text
Expense
```

### Step 3

Enter the description.

Example:

```text
Groceries
```

### Step 4

Select a category.

Example:

```text
Food
```

### Step 5

Enter the amount.

Example:

```text
3500
```

### Step 6

Select the date.

### Step 7

Submit the form.

The expense will appear in the transaction list.

The total expenses and balance will be recalculated.

---

# 10. Viewing Transactions

The transaction section displays stored financial records.

A transaction may contain:

```text
Type
Description
Category
Amount
Date
Actions
```

The user can use the transaction list to review financial activity.

---

# 11. Editing a Transaction

To edit an existing transaction:

1. Locate the transaction.
2. Select the **Edit** option.
3. Modify the required information.
4. Submit the updated information.
5. The application validates the data.
6. The transaction is updated.
7. LocalStorage is updated.
8. Dashboard values are recalculated.

The updated transaction should immediately appear in the transaction list.

---

# 12. Deleting a Transaction

To delete a transaction:

1. Locate the transaction.
2. Select the **Delete** option.
3. The transaction is removed.
4. Application data is updated.
5. Financial totals are recalculated.
6. The dashboard is refreshed.

The deleted transaction should no longer appear in the transaction list.

---

# 13. Searching Transactions

The application provides a search field.

To search:

1. Click the search field.
2. Enter a keyword.
3. The application searches the available transaction information.
4. Matching transactions are displayed.

Example:

```text
Search:
Groceries
```

The application should display transactions related to the search term.

---

# 14. Filtering Transactions

The application allows users to filter transaction records.

Depending on the available interface, filters may include:

- Income
- Expense
- Category
- Other supported criteria

To apply a filter:

1. Select the desired filter.
2. The application evaluates the transaction records.
3. Matching records are displayed.

To view all records again, clear or reset the filter.

---

# 15. Setting a Monthly Budget

The monthly budget represents the amount the user plans to spend during the selected budgeting period.

To set a budget:

1. Open the Budget section.
2. Enter the desired amount.
3. Submit the budget.
4. The system validates the amount.
5. The budget is stored.
6. Budget usage is recalculated.

Example:

```text
Monthly Budget:
₹15,000
```

---

# 16. Monitoring Budget Usage

After setting a budget, the dashboard displays budget-related information.

The user can monitor:

- Configured budget.
- Amount spent.
- Remaining budget.
- Budget utilization.
- Budget status.

Conceptually:

```text
Budget Remaining
=
Budget - Relevant Expenses
```

If expenses exceed the configured budget, the application can indicate that the budget has been exceeded.

---

# 17. Setting a Savings Goal

The savings goal represents the amount the user wants to save.

To set a savings goal:

1. Open the Savings section.
2. Enter the target amount.
3. Submit the value.
4. The application validates the value.
5. The goal is stored.
6. Savings progress is calculated.

Example:

```text
Savings Goal:
₹10,000
```

---

# 18. Monitoring Savings Progress

The savings section allows the user to monitor progress toward the configured goal.

The application uses available financial information to calculate savings progress.

Conceptually:

```text
Savings Progress
=
Current Savings / Savings Goal × 100
```

The dashboard displays the resulting progress.

---

# 19. Category Analysis

The category analysis section helps users understand where their money is being spent.

Example categories:

```text
Food
Transport
Bills
Shopping
Entertainment
Other
```

For example:

```text
Food
├── Groceries ₹3,500
├── Restaurant ₹800
└── Snacks ₹200
```

The application can calculate:

```text
Food Total = ₹4,500
```

This allows users to identify major spending categories.

---

# 20. Exporting Transactions

The application allows transaction data to be exported as a CSV file.

To export:

1. Open the transaction section.
2. Ensure transaction data is available.
3. Select **Export CSV**.
4. The application prepares the transaction data.
5. A CSV file is generated.
6. The browser downloads the file.

The exported data may contain:

```text
ID
Type
Description
Category
Amount
Date
```

The CSV file can be opened using spreadsheet software such as Microsoft Excel or Google Sheets.

---

# 21. Resetting Demo Data

The application provides a reset option for returning to the demonstration state.

To reset:

1. Select **Reset Demo Data**.
2. Confirm the operation if confirmation is displayed.
3. Existing application data is cleared/reset.
4. Default demonstration data is restored.
5. Dashboard information is recalculated.

This feature is particularly useful when demonstrating the project repeatedly.

---

# 22. LocalStorage Persistence

The application stores its data in Browser LocalStorage.

The main logical storage key is:

```text
budgetPlanningApplication
```

Data stored may include:

```text
Transactions
Budget
Savings Goal
```

Because the data is stored locally, refreshing the browser normally does not remove the saved information.

---

# 23. Clearing Application Data

If the user wants to completely remove local application data, browser developer tools can be used.

General procedure:

1. Open browser developer tools.
2. Open the **Application/Storage** section.
3. Locate LocalStorage.
4. Locate the application's storage entry.
5. Remove the stored data.
6. Reload the application.

After clearing the data, the application may initialize with its default/demo state.

---

# 24. Validation Messages

The application validates important user inputs.

Examples of invalid inputs include:

```text
Empty description
Invalid amount
Zero amount
Negative amount
Missing category
Invalid budget
Invalid savings goal
```

When invalid data is entered, the application should display an appropriate validation message and prevent invalid information from being stored.

---

# 25. Recommended Usage Workflow

A typical user workflow is:

```text
Open Application
      ↓
View Dashboard
      ↓
Add Income
      ↓
Add Expenses
      ↓
Set Monthly Budget
      ↓
Set Savings Goal
      ↓
Monitor Dashboard
      ↓
Search / Filter Transactions
      ↓
View Category Analysis
      ↓
Export Data
```

---

# 26. Example Monthly Usage

Consider the following example.

### Income

```text
Salary = ₹30,000
```

### Expenses

```text
Groceries = ₹3,500
Bus Pass = ₹1,200
```

### Budget

```text
₹15,000
```

### Savings Goal

```text
₹10,000
```

The dashboard can then provide a summarized view of:

```text
Total Income
Total Expenses
Current Balance
Budget Status
Savings Progress
Category Analysis
```

---

# 27. Troubleshooting

## Problem 1 — Application Does Not Open

### Possible Causes

- Incorrect file path.
- Browser issue.
- Missing project files.

### Solution

Verify that:

```text
src/index.html
src/style.css
src/script.js
```

are present.

---

## Problem 2 — Styling Is Not Displayed

### Possible Causes

- Incorrect CSS path.
- Missing `style.css`.
- Browser cache.

### Solution

Verify that `index.html` correctly references `style.css`.

Refresh the browser after checking the file path.

---

## Problem 3 — JavaScript Features Do Not Work

### Possible Causes

- Incorrect JavaScript path.
- JavaScript syntax error.
- Browser console error.

### Solution

1. Open browser Developer Tools.
2. Open the Console.
3. Check for JavaScript errors.
4. Verify the `script.js` path.
5. Reload the page.

---

## Problem 4 — Data Disappears

### Possible Causes

- Browser LocalStorage was cleared.
- Browser storage was manually deleted.
- Application reset was performed.

### Solution

Check Browser LocalStorage and verify that application data exists.

---

## Problem 5 — CSV Export Does Not Work

### Possible Causes

- No transaction data exists.
- Browser download restrictions.
- JavaScript error.

### Solution

1. Add at least one transaction.
2. Try the export option again.
3. Check browser console for errors.
4. Check the browser download settings.

---

# 28. Data Privacy

The current application stores financial information locally in the browser.

The application does not require:

- Online account registration.
- Password.
- Bank login.
- Payment credentials.

However, users should remember that browser storage is not a secure replacement for a professional financial database.

Sensitive financial credentials should not be stored in the application.

---

# 29. Backup Recommendation

Users can use the CSV export feature to create a manual backup of transaction records.

Recommended workflow:

```text
Application
     ↓
Export CSV
     ↓
Downloaded CSV
     ↓
Secure Backup Location
```

For important financial information, the exported file should be stored securely.

---

# 30. Limitations

The current version has the following limitations:

- No user authentication.
- No multi-user functionality.
- No cloud synchronization.
- No bank integration.
- No online payment processing.
- LocalStorage-based data storage.
- No automatic cloud backup.
- Limited advanced financial analytics.

These limitations can be addressed in future versions.

---

# 31. Future Enhancements

Possible future improvements include:

- User registration and authentication.
- Cloud database.
- Multiple financial accounts.
- Advanced charts.
- Monthly and yearly reports.
- Recurring transactions.
- Financial notifications.
- Expense recommendations.
- Mobile application.
- Bank account integration.
- Cloud backup.
- Multi-device synchronization.
- AI-based financial insights.

---

# 32. Quick Reference

| Task | Action |
|---|---|
| Open Application | Open `src/index.html` |
| Add Income | Select Income and submit details |
| Add Expense | Select Expense and submit details |
| Edit | Select Edit on a transaction |
| Delete | Select Delete |
| Search | Enter keyword |
| Filter | Select filter |
| Budget | Enter monthly budget |
| Savings | Enter savings goal |
| Analysis | View category analysis |
| Export | Select Export CSV |
| Reset | Select Reset Demo Data |

---

# 33. User Workflow Summary

The complete user workflow can be summarized as:

```text
                ┌──────────────┐
                │    START     │
                └──────┬───────┘
                       ↓
              Open Application
                       ↓
                View Dashboard
                       ↓
             ┌─────────┴─────────┐
             ↓                   ↓
       Add Transactions     Set Financial Goals
             ↓                   ↓
       Income / Expense     Budget / Savings
             └─────────┬─────────┘
                       ↓
                Monitor Dashboard
                       ↓
                Search / Filter
                       ↓
              Category Analysis
                       ↓
                  Export Data
                       ↓
                     END
```

---

# 34. User Acceptance Checklist

Before considering the application ready for use, verify:

- [ ] Application opens successfully.
- [ ] Dashboard displays correctly.
- [ ] Income can be added.
- [ ] Expenses can be added.
- [ ] Transactions can be edited.
- [ ] Transactions can be deleted.
- [ ] Search works.
- [ ] Filtering works.
- [ ] Budget can be configured.
- [ ] Budget usage is displayed.
- [ ] Savings goal can be configured.
- [ ] Savings progress is displayed.
- [ ] Category analysis works.
- [ ] CSV export works.
- [ ] LocalStorage persistence works.
- [ ] Reset functionality works.
- [ ] Application works on a mobile-sized screen.

---

# 35. Conclusion

The User Manual provides step-by-step instructions for using the Budget Planning Application.

Users can manage income and expenses, configure budgets and savings goals, analyze financial data, search and filter transactions, export records, and maintain data using browser-based persistence.

The manual also provides troubleshooting guidance, data privacy information, limitations, and future enhancement possibilities.

---

## Project Information

**Project:** Budget Planning Application  
**Document:** User Manual  
**Author:** Ansh Pandey  
**Year:** 2026  
**Version:** 1.0  
**Status:** Academic Project
