# Database and Data Storage Design — Budget Planning Application

**Project Name:** Budget Planning Application  
**Document:** Database and Data Storage Design  
**Author:** Ansh Pandey  
**Year:** 2026  
**Technology:** HTML5, CSS3, JavaScript ES6, Browser LocalStorage  
**Version:** 1.0

---

# 1. Introduction

The Database and Data Storage Design document describes how application data is structured, stored, retrieved, updated, and managed in the Budget Planning Application.

The current version of the application is a client-side web application and uses **Browser LocalStorage** for persistent data storage.

No external SQL or NoSQL database is required in the current implementation.

However, the logical data model has been designed so that the application can be migrated to a backend database in a future version.

---

# 2. Purpose

The objectives of this document are:

- To define the application's data storage mechanism.
- To describe the structure of stored data.
- To define the main data fields.
- To explain CRUD operations.
- To describe data validation rules.
- To define data persistence behavior.
- To document LocalStorage usage.
- To provide a foundation for future database migration.

---

# 3. Current Storage Technology

The current application uses:

```text
Browser LocalStorage
```

LocalStorage provides client-side key-value storage.

The application stores its main state under the following logical key:

```text
budgetPlanningApplication
```

The data is stored in serialized JSON format.

---

# 4. Storage Architecture

The current data storage architecture is:

```text
┌─────────────────────────────┐
│            User             │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│      Web Application        │
│      HTML/CSS/JavaScript    │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│       Application State     │
│                             │
│  Transactions               │
│  Budget                     │
│  Savings Goal               │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│       Browser LocalStorage  │
└─────────────────────────────┘
```

---

# 5. Main Data Object

The application's logical state can be represented as:

```json
{
  "transactions": [],
  "budget": 15000,
  "savingsGoal": 10000
}
```

The actual object may contain transaction records inside the `transactions` array.

---

# 6. Transaction Data Structure

Each transaction contains the following information:

```json
{
  "id": 1,
  "type": "expense",
  "description": "Groceries",
  "category": "Food",
  "amount": 3500,
  "date": "2026-10-01"
}
```

---

# 7. Transaction Data Dictionary

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | Number/String | Yes | Unique transaction identifier |
| `type` | String | Yes | Income or expense |
| `description` | String | Yes | Description of transaction |
| `category` | String | Yes | Financial category |
| `amount` | Number | Yes | Monetary amount |
| `date` | String/Date | Yes | Transaction date |

---

# 8. Budget Data

The application stores the monthly budget as a numerical value.

Example:

```json
{
  "budget": 15000
}
```

The budget is used for:

- Spending limit
- Budget utilization
- Remaining budget
- Budget status

---

# 9. Savings Goal Data

The application stores the target savings amount.

Example:

```json
{
  "savingsGoal": 10000
}
```

The value is used to calculate:

- Current savings
- Savings progress
- Goal completion percentage

---

# 10. LocalStorage Key

The primary application storage key is:

```text
budgetPlanningApplication
```

Conceptually:

```javascript
localStorage.setItem(
    "budgetPlanningApplication",
    JSON.stringify(appData)
);
```

To retrieve the data:

```javascript
const appData = JSON.parse(
    localStorage.getItem("budgetPlanningApplication")
);
```

The exact implementation may vary depending on the final `script.js`.

---

# 11. Complete Sample Data

A representative application state can be:

```json
{
  "transactions": [
    {
      "id": 1,
      "type": "income",
      "description": "Salary",
      "category": "Salary",
      "amount": 30000,
      "date": "2026-10-01"
    },
    {
      "id": 2,
      "type": "expense",
      "description": "Groceries",
      "category": "Food",
      "amount": 3500,
      "date": "2026-10-02"
    },
    {
      "id": 3,
      "type": "expense",
      "description": "Bus Pass",
      "category": "Transport",
      "amount": 1200,
      "date": "2026-10-03"
    }
  ],
  "budget": 15000,
  "savingsGoal": 10000
}
```

---

# 12. CRUD Operations

The application supports CRUD operations for transaction data.

CRUD stands for:

- Create
- Read
- Update
- Delete

---

## 12.1 Create

The Create operation adds a new transaction.

### Process

```text
User Input
    ↓
Validation
    ↓
Create Transaction Object
    ↓
Add to Transactions Array
    ↓
Save to LocalStorage
```

Example:

```javascript
const transaction = {
    id: Date.now(),
    type: "expense",
    description: "Groceries",
    category: "Food",
    amount: 3500,
    date: "2026-10-01"
};
```

---

## 12.2 Read

The Read operation retrieves stored application data.

```text
LocalStorage
     ↓
JSON Parse
     ↓
Application State
     ↓
Dashboard / Transaction Table
```

Example:

```javascript
const data = localStorage.getItem(
    "budgetPlanningApplication"
);
```

---

## 12.3 Update

The Update operation modifies an existing transaction or setting.

```text
Existing Data
     ↓
Edit Form
     ↓
Validation
     ↓
Update Object
     ↓
Save Updated State
```

---

## 12.4 Delete

The Delete operation removes a transaction.

```text
Selected Transaction
       ↓
Identify ID
       ↓
Remove Transaction
       ↓
Save Updated State
       ↓
Refresh UI
```

---

# 13. Data Validation Rules

The application should validate all important user inputs.

## Transaction Validation

A transaction must contain:

- Transaction type
- Description
- Category
- Amount
- Date

### Amount Validation

The amount should be:

```text
Amount > 0
```

### Transaction Type

Valid transaction types are:

```text
income
expense
```

### Date

The date should be a valid date value.

---

# 14. Budget Validation

The monthly budget should:

- Be provided by the user.
- Be numeric.
- Be greater than zero.
- Be stored only after successful validation.

Example:

```text
15000 ✓
0     ✗
-500  ✗
abc   ✗
```

---

# 15. Savings Goal Validation

The savings goal should:

- Be numeric.
- Be greater than zero.
- Be stored only after validation.

Example:

```text
10000 ✓
0     ✗
-1000 ✗
abc   ✗
```

---

# 16. Data Persistence

One of the main advantages of LocalStorage in the current application is persistence across browser page refreshes.

The general flow is:

```text
User Action
     ↓
Application State Changes
     ↓
JSON.stringify()
     ↓
LocalStorage
     ↓
Browser Storage
```

When the application starts:

```text
LocalStorage
     ↓
JSON.parse()
     ↓
Application State
     ↓
Dashboard
```

---

# 17. Data Update Flow

Whenever application data changes:

```text
Create / Edit / Delete
          ↓
   Update Application State
          ↓
      Save State
          ↓
      LocalStorage
          ↓
    Recalculate Values
          ↓
      Refresh UI
```

This ensures that the interface reflects the latest stored information.

---

# 18. Financial Calculations

The stored transaction data is used to generate financial statistics.

## Total Income

```text
Total Income
=
Sum of all income transactions
```

## Total Expenses

```text
Total Expenses
=
Sum of all expense transactions
```

## Balance

```text
Balance
=
Total Income - Total Expenses
```

## Budget Usage

Conceptually:

```text
Budget Usage %
=
Expenses / Budget × 100
```

## Savings Progress

Conceptually:

```text
Savings Progress %
=
Current Savings / Savings Goal × 100
```

The final calculation should follow the implementation in `script.js`.

---

# 19. Category-Based Data

Transactions contain category information.

Example:

```text
Food
Transport
Bills
Shopping
Entertainment
Salary
Other
```

This data supports category analysis.

Example:

```text
Food
├── Groceries ₹3500
├── Restaurant ₹800
└── Snacks ₹200

Total = ₹4500
```

---

# 20. Search Data Processing

The search functionality reads transaction data from application state.

```text
Search Keyword
       ↓
Transactions Array
       ↓
Compare Description / Category
       ↓
Matching Transactions
       ↓
Display Results
```

---

# 21. Filter Data Processing

The filter process can filter transactions according to available criteria.

```text
Filter Selection
       ↓
Transactions Array
       ↓
Apply Filter
       ↓
Matching Records
       ↓
Display Results
```

---

# 22. CSV Export Data Processing

The export feature converts transaction data into CSV format.

```text
Transactions
     ↓
Read Records
     ↓
Create CSV Headers
     ↓
Create CSV Rows
     ↓
Generate CSV Content
     ↓
Create Download File
     ↓
Browser Download
```

Example CSV structure:

```text
id,type,description,category,amount,date
1,income,Salary,Salary,30000,2026-10-01
2,expense,Groceries,Food,3500,2026-10-02
3,expense,Bus Pass,Transport,1200,2026-10-03
```

---

# 23. Data Consistency

The application should maintain consistent application state.

Whenever a transaction is added, edited, or deleted:

1. Transaction state must be updated.
2. LocalStorage must be updated.
3. Total income must be recalculated.
4. Total expenses must be recalculated.
5. Balance must be recalculated.
6. Budget information must be refreshed.
7. Savings information must be refreshed.
8. Dashboard must be updated.

---

# 24. Data Integrity

Data integrity is maintained using:

- Unique transaction IDs.
- Input validation.
- Numeric validation.
- Required field validation.
- Controlled transaction types.
- Consistent object structure.
- LocalStorage serialization.
- State synchronization.

---

# 25. Storage Limitations

LocalStorage is suitable for this academic project but has limitations.

### Limitations

- Data is stored only in the browser.
- Data is not automatically synchronized across devices.
- There is no server-side backup.
- There is no multi-user support.
- There is no database query engine.
- LocalStorage is not designed for highly sensitive information.
- Clearing browser storage can remove application data.

---

# 26. Data Security

The current application does not implement server-side security because it is a client-side application.

Therefore, LocalStorage should not be used to store:

- Passwords
- Banking credentials
- Authentication secrets
- Credit card details
- Highly sensitive personal information

A future full-stack version should introduce secure authentication and server-side storage.

---

# 27. Future Database Design

If the application is converted into a full-stack application, a database can be introduced.

A possible relational database design is:

```text
USERS
-------------------------
user_id PK
name
email
password_hash


CATEGORIES
-------------------------
category_id PK
category_name
category_type


TRANSACTIONS
-------------------------
transaction_id PK
user_id FK
category_id FK
type
description
amount
transaction_date


BUDGETS
-------------------------
budget_id PK
user_id FK
month
year
amount


SAVINGS_GOALS
-------------------------
goal_id PK
user_id FK
goal_name
target_amount
current_amount
target_date
```

This is a **future design** and is not part of the current LocalStorage implementation.

---

# 28. Future Database Relationships

A future full-stack implementation could use:

```text
USER
 │
 ├──────────────< TRANSACTION
 │
 ├──────────────< BUDGET
 │
 └──────────────< SAVINGS_GOAL

CATEGORY
 │
 └──────────────< TRANSACTION
```

This would support multiple users and persistent server-side data.

---

# 29. Possible Database Technologies

Future versions could use:

### Relational Database

- MySQL
- PostgreSQL
- SQLite

### NoSQL Database

- MongoDB

The choice would depend on the backend architecture and project requirements.

---

# 30. Backup and Recovery

### Current System

The current system does not provide automatic cloud backup.

Users can manually export transaction data using CSV.

```text
Application Data
       ↓
Export CSV
       ↓
Downloaded File
       ↓
Manual Backup
```

### Future System

A backend implementation could provide:

- Automated backups.
- Cloud storage.
- Database recovery.
- Versioned backups.
- Multi-device synchronization.

---

# 31. Data Migration Strategy

If the application is migrated from LocalStorage to a backend database, the following process can be used:

```text
LocalStorage Data
       ↓
Export JSON / CSV
       ↓
Data Validation
       ↓
Data Transformation
       ↓
Database Import
       ↓
Backend Application
```

The migration process should preserve transaction information and financial values.

---

# 32. Data Design and Software Engineering

The data design supports important Software Engineering principles:

### Modularity

Financial data is logically separated into transactions, budget, savings, and categories.

### Maintainability

A structured data model makes future changes easier.

### Scalability

The logical model can be migrated to a backend database.

### Reliability

Data persistence reduces loss during page refreshes.

### Testability

Structured data allows CRUD and validation operations to be tested independently.

---

# 33. Database Design Validation Checklist

- [x] Current storage mechanism documented.
- [x] LocalStorage key documented.
- [x] Transaction structure defined.
- [x] Budget structure defined.
- [x] Savings goal structure defined.
- [x] Data dictionary provided.
- [x] CRUD operations documented.
- [x] Validation rules documented.
- [x] Data persistence explained.
- [x] Data integrity rules defined.
- [x] Search and filter processing documented.
- [x] CSV export documented.
- [x] Future database model provided.
- [x] Future relationships documented.
- [x] Backup strategy documented.
- [x] Migration strategy documented.

---

# 34. Conclusion

The Budget Planning Application currently uses Browser LocalStorage to provide simple and persistent client-side data storage.

The data model consists primarily of transaction records, budget information, savings goals, and category information. The application supports creating, reading, updating, and deleting transaction data while dynamically generating financial summaries.

Although the current application does not require a traditional database, the logical structure has been designed to support future migration to a relational or NoSQL database.

This design provides a clear foundation for implementation, maintenance, testing, and future scalability.

---

## Project Information

**Project:** Budget Planning Application  
**Document:** Database and Data Storage Design  
**Author:** Ansh Pandey  
**Year:** 2026  
**Version:** 1.0  
**Status:** Academic Project
