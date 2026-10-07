# Flowchart — Budget Planning Application

**Project Name:** Budget Planning Application  
**Document:** System Flowcharts  
**Author:** Ansh Pandey  
**Year:** 2026  
**Technology:** HTML5, CSS3, JavaScript ES6, Browser LocalStorage  
**Version:** 1.0

---

# 1. Introduction

A **flowchart** is a graphical representation of the sequence of operations performed by a system.

The flowcharts for the Budget Planning Application describe how the application processes user actions such as adding transactions, calculating financial summaries, managing budgets, tracking savings, searching records, and exporting data.

Flowcharts help developers and users understand the logical sequence of operations and decision-making points within the system.

---

# 2. Purpose

The objectives of the flowchart documentation are:

- To represent application workflows visually.
- To describe the sequence of major operations.
- To identify decision points.
- To represent validation and error handling.
- To simplify understanding of application logic.
- To support implementation and testing.

---

# 3. Flowchart Symbols

The following standard flowchart concepts are used:

| Symbol / Concept | Meaning |
|---|---|
| Start / End | Beginning or termination of a process |
| Process | An operation performed by the system |
| Input / Output | Data entered or displayed |
| Decision | Conditional check |
| Arrow | Direction of flow |
| Data Store | Stored application information |

---

# 4. Overall Application Flowchart

The overall application workflow begins when the user opens the application.

```mermaid
flowchart TD

    A([Start])
    B["Load Budget Planning Application"]
    C["Load Data from LocalStorage"]
    D{"Data Available?"}

    E["Initialize Default / Demo Data"]
    F["Display Dashboard"]

    G{"User Action?"}

    H["Manage Transactions"]
    I["Manage Budget"]
    J["Manage Savings Goal"]
    K["Search / Filter"]
    L["View Category Analysis"]
    M["Export Transactions"]
    N["Reset Demo Data"]

    O["Validate Input"]
    P{"Input Valid?"}
    Q["Display Error Message"]

    R["Save Updated Data"]
    S["Recalculate Financial Summary"]
    T["Refresh Dashboard"]

    U([End])

    A --> B
    B --> C
    C --> D

    D -- "No" --> E
    D -- "Yes" --> F
    E --> F

    F --> G

    G -- "Transaction" --> H
    G -- "Budget" --> I
    G -- "Savings Goal" --> J
    G -- "Search / Filter" --> K
    G -- "Analysis" --> L
    G -- "Export" --> M
    G -- "Reset" --> N

    H --> O
    I --> O
    J --> O

    O --> P

    P -- "No" --> Q
    Q --> G

    P -- "Yes" --> R
    R --> S
    S --> T
    T --> G

    K --> T
    L --> T
    M --> T
    N --> T

    G -- "Exit" --> U
```

---

# 5. Application Initialization Flowchart

This flowchart describes what happens when the application starts.

```mermaid
flowchart TD

    A([Start])
    B["Open Application"]
    C["Initialize JavaScript"]
    D["Read LocalStorage"]
    E{"Saved Data Exists?"}

    F["Load Saved Data"]
    G["Load Default / Demo Data"]
    H["Store Initial Data"]
    I["Calculate Financial Summary"]
    J["Render Dashboard"]
    K([Application Ready])

    A --> B
    B --> C
    C --> D
    D --> E

    E -- "Yes" --> F
    E -- "No" --> G
    G --> H

    F --> I
    H --> I
    I --> J
    J --> K
```

---

# 6. Add Transaction Flowchart

The transaction workflow handles both income and expense records.

```mermaid
flowchart TD

    A([Start])
    B["Open Transaction Form"]
    C["Select Transaction Type"]
    D["Enter Description"]
    E["Select Category"]
    F["Enter Amount"]
    G["Select Date"]
    H["Submit Form"]

    I["Validate Transaction"]
    J{"Valid?"}

    K["Display Validation Error"]
    L["Create Transaction Object"]
    M["Add Transaction to State"]
    N["Save Data to LocalStorage"]
    O["Recalculate Totals"]
    P["Refresh Transaction List"]
    Q["Refresh Dashboard"]
    R([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J

    J -- "No" --> K
    K --> B

    J -- "Yes" --> L
    L --> M
    M --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
```

---

# 7. Add Income Flow

Income follows the transaction workflow with the transaction type set to income.

```text
Start
  ↓
Open Transaction Form
  ↓
Select Income
  ↓
Enter Details
  ↓
Validate Data
  ↓
Valid?
 ┌───────────────┐
 │               │
No              Yes
 │               │
 ↓               ↓
Error         Create Income
Message           ↓
 │            Save Data
 │               ↓
 └──────────► Update Dashboard
                  ↓
                 End
```

---

# 8. Add Expense Flow

Expense follows the same general transaction workflow.

```text
Start
  ↓
Open Transaction Form
  ↓
Select Expense
  ↓
Enter Details
  ↓
Validate Data
  ↓
Valid?
 ┌───────────────┐
 │               │
No              Yes
 │               │
 ↓               ↓
Error         Create Expense
Message           ↓
 │            Save Data
 │               ↓
 └──────────► Update Totals
                  ↓
            Update Dashboard
                  ↓
                 End
```

---

# 9. Edit Transaction Flowchart

```mermaid
flowchart TD

    A([Start])
    B["Select Existing Transaction"]
    C["Click Edit"]
    D["Load Transaction Details"]
    E["Modify Information"]
    F["Submit Changes"]
    G["Validate Updated Data"]
    H{"Valid?"}

    I["Display Error"]
    J["Update Transaction"]
    K["Save to LocalStorage"]
    L["Recalculate Financial Data"]
    M["Refresh UI"]
    N([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H

    H -- "No" --> I
    I --> E

    H -- "Yes" --> J
    J --> K
    K --> L
    L --> M
    M --> N
```

---

# 10. Delete Transaction Flowchart

```mermaid
flowchart TD

    A([Start])
    B["Select Transaction"]
    C["Click Delete"]
    D{"Transaction Exists?"}

    E["Display Error / No Action"]
    F["Remove Transaction"]
    G["Update LocalStorage"]
    H["Recalculate Financial Data"]
    I["Refresh Transaction List"]
    J["Refresh Dashboard"]
    K([End])

    A --> B
    B --> C
    C --> D

    D -- "No" --> E
    E --> K

    D -- "Yes" --> F
    F --> G
    G --> H
    H --> I
    I --> J
    J --> K
```

---

# 11. Budget Management Flowchart

The budget workflow allows the user to configure a monthly spending limit.

```mermaid
flowchart TD

    A([Start])
    B["Open Budget Section"]
    C["Enter Monthly Budget"]
    D["Submit Budget"]
    E["Validate Budget"]
    F{"Valid Amount?"}

    G["Display Error Message"]
    H["Save Budget"]
    I["Store in LocalStorage"]
    J["Calculate Budget Usage"]
    K["Calculate Remaining Budget"]
    L["Display Budget Status"]
    M([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F

    F -- "No" --> G
    G --> C

    F -- "Yes" --> H
    H --> I
    I --> J
    J --> K
    K --> L
    L --> M
```

---

# 12. Budget Monitoring Flowchart

```mermaid
flowchart TD

    A([Start])
    B["Retrieve Monthly Budget"]
    C["Calculate Relevant Expenses"]
    D["Calculate Budget Usage"]
    E["Calculate Remaining Budget"]
    F{"Budget Exceeded?"}

    G["Display Budget Within Limit"]
    H["Display Budget Exceeded Warning"]
    I["Update Dashboard"]
    J([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F

    F -- "No" --> G
    F -- "Yes" --> H

    G --> I
    H --> I
    I --> J
```

---

# 13. Savings Goal Flowchart

```mermaid
flowchart TD

    A([Start])
    B["Open Savings Section"]
    C["Enter Savings Goal"]
    D["Submit Goal"]
    E["Validate Goal"]
    F{"Valid?"}

    G["Display Error Message"]
    H["Save Savings Goal"]
    I["Store in LocalStorage"]
    J["Calculate Current Savings"]
    K["Calculate Savings Progress"]
    L["Display Progress"]
    M([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F

    F -- "No" --> G
    G --> C

    F -- "Yes" --> H
    H --> I
    I --> J
    J --> K
    K --> L
    L --> M
```

---

# 14. Search Flowchart

```mermaid
flowchart TD

    A([Start])
    B["Enter Search Keyword"]
    C["Read Transaction Data"]
    D["Compare Keyword"]
    E{"Matching Records?"}

    F["Display Matching Transactions"]
    G["Display No Matching Records"]

    H([End])

    A --> B
    B --> C
    C --> D
    D --> E

    E -- "Yes" --> F
    E -- "No" --> G

    F --> H
    G --> H
```

---

# 15. Filter Flowchart

```mermaid
flowchart TD

    A([Start])
    B["Select Filter"]
    C["Read Transactions"]
    D["Apply Filter"]
    E{"Matching Records?"}

    F["Display Filtered Records"]
    G["Display Empty Result"]

    H([End])

    A --> B
    B --> C
    C --> D
    D --> E

    E -- "Yes" --> F
    E -- "No" --> G

    F --> H
    G --> H
```

---

# 16. Category Analysis Flowchart

The category analysis process groups expense transactions by category.

```mermaid
flowchart TD

    A([Start])
    B["Retrieve Transactions"]
    C["Select Expense Transactions"]
    D["Group Expenses by Category"]
    E["Calculate Category Totals"]
    F["Generate Category Analysis"]
    G["Display Category-wise Spending"]
    H([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
```

---

# 17. Financial Calculation Flowchart

The dashboard calculations follow this general process:

```mermaid
flowchart TD

    A([Start])
    B["Retrieve Transactions"]
    C["Separate Income and Expenses"]
    D["Calculate Total Income"]
    E["Calculate Total Expenses"]
    F["Calculate Balance"]
    G["Retrieve Budget"]
    H["Calculate Budget Usage"]
    I["Retrieve Savings Goal"]
    J["Calculate Savings Progress"]
    K["Update Dashboard"]
    L([End])

    A --> B
    B --> C
    C --> D
    C --> E

    D --> F
    E --> F

    F --> G
    G --> H

    H --> I
    I --> J

    J --> K
    K --> L
```

---

# 18. Financial Calculation Logic

## 18.1 Total Income

```text
Total Income = Sum of all Income Transactions
```

## 18.2 Total Expenses

```text
Total Expenses = Sum of all Expense Transactions
```

## 18.3 Current Balance

```text
Current Balance = Total Income - Total Expenses
```

## 18.4 Budget Usage

```text
Budget Usage = Relevant Expenses / Monthly Budget × 100
```

## 18.5 Savings Progress

```text
Savings Progress = Current Savings / Savings Goal × 100
```

The exact calculation may depend on the implementation logic used in `script.js`.

---

# 19. CSV Export Flowchart

```mermaid
flowchart TD

    A([Start])
    B["User Clicks Export CSV"]
    C["Retrieve Transaction Data"]
    D{"Transactions Available?"}

    E["Generate CSV Headers"]
    F["Convert Transactions to CSV Rows"]
    G["Create CSV File"]
    H["Trigger Browser Download"]

    I["Display No Data Message"]

    J([End])

    A --> B
    B --> C
    C --> D

    D -- "Yes" --> E
    E --> F
    F --> G
    G --> H
    H --> J

    D -- "No" --> I
    I --> J
```

---

# 20. Reset Demo Data Flowchart

```mermaid
flowchart TD

    A([Start])
    B["User Clicks Reset Demo Data"]
    C{"Confirm Reset?"}

    D["Cancel Operation"]
    E["Clear Existing Application Data"]
    F["Load Default Demo Data"]
    G["Save Demo Data"]
    H["Recalculate Financial Summary"]
    I["Refresh Dashboard"]
    J([End])

    A --> B
    B --> C

    C -- "No" --> D
    D --> J

    C -- "Yes" --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J
```

---

# 21. Data Persistence Flowchart

All important application data is persisted using LocalStorage.

```text
User Action
    ↓
Application State Updated
    ↓
Validation
    ↓
Valid?
 ┌─────────────┐
 │             │
No            Yes
 │             │
 ↓             ↓
Error      LocalStorage
Message        ↓
           Data Saved
               ↓
          UI Refreshed
```

---

# 22. Error Handling Flow

The application performs validation before storing user-provided data.

```mermaid
flowchart TD

    A([User Input])
    B["Validate Input"]
    C{"Input Valid?"}

    D["Continue Processing"]
    E["Display Error Message"]
    F["Do Not Save Invalid Data"]
    G([End])

    A --> B
    B --> C

    C -- "Yes" --> D
    D --> G

    C -- "No" --> E
    E --> F
    F --> G
```

---

# 23. Complete Transaction Lifecycle

The complete lifecycle of a transaction can be represented as:

```text
Create
  ↓
Validate
  ↓
Store
  ↓
Display
  ↓
Search / Filter
  ↓
Edit
  ↓
Validate
  ↓
Store Updated Data
  ↓
Display Updated Data
  ↓
Delete
  ↓
Update Storage
```

---

# 24. Decision Points

The major decision points in the application are:

| Decision | Possible Outcomes |
|---|---|
| Saved data available? | Yes / No |
| Input valid? | Yes / No |
| Transaction exists? | Yes / No |
| Matching search results? | Yes / No |
| Matching filter results? | Yes / No |
| Budget exceeded? | Yes / No |
| Savings goal available? | Yes / No |
| Transactions available for export? | Yes / No |
| Reset confirmed? | Yes / No |

---

# 25. Flowchart Relationship With System Modules

| Flowchart | Related Module |
|---|---|
| Application Initialization | Application Core |
| Add Transaction | Transaction Management |
| Edit Transaction | Transaction Management |
| Delete Transaction | Transaction Management |
| Budget Management | Budget Module |
| Savings Goal | Savings Module |
| Search | Search Module |
| Filter | Filter Module |
| Category Analysis | Analysis Module |
| Financial Calculation | Dashboard Module |
| CSV Export | Export Module |
| Reset Demo Data | Data Management |
| Error Handling | Validation Module |

---

# 26. Flowchart Validation Checklist

- [x] Application startup flow included.
- [x] Transaction flow included.
- [x] Income flow included.
- [x] Expense flow included.
- [x] Edit flow included.
- [x] Delete flow included.
- [x] Budget flow included.
- [x] Savings flow included.
- [x] Search flow included.
- [x] Filter flow included.
- [x] Category analysis flow included.
- [x] Financial calculation flow included.
- [x] CSV export flow included.
- [x] Reset flow included.
- [x] Validation flow included.
- [x] Error handling included.
- [x] Decision points documented.

---

# 27. Conclusion

The flowcharts provide a visual representation of the major workflows of the Budget Planning Application.

They describe how the system initializes, receives user input, validates information, stores data, performs financial calculations, updates the dashboard, and provides outputs to the user.

The flowcharts also cover important decision points and error-handling paths, making them useful for system implementation, debugging, testing, and academic Software Engineering documentation.

---

## Project Information

**Project:** Budget Planning Application  
**Document:** System Flowcharts  
**Author:** Ansh Pandey  
**Year:** 2026  
**Version:** 1.0  
**Status:** Academic Project
