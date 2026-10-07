# SYSTEM DESIGN DOCUMENT

# Budget Planning Application

**Project Type:** Software Engineering Project  
**Developer:** Ansh Pandey  
**Version:** 1.0  
**Year:** 2026

---

# 1. Introduction

## 1.1 Purpose

The purpose of this System Design Document is to describe the technical and structural design of the **Budget Planning Application**.

The SRS document defines what the system should do. This document explains how the requirements will be transformed into a working software system.

The design focuses on:

- System architecture
- Application modules
- Component responsibilities
- Data structures
- Data flow
- User interface structure
- Storage design
- Validation
- Error handling
- Scalability
- Maintainability

---

# 2. System Overview

The Budget Planning Application is a browser-based personal finance management application.

The system allows users to:

- Record income.
- Record expenses.
- Edit transactions.
- Delete transactions.
- Set monthly budgets.
- Track budget utilization.
- Set savings goals.
- Monitor savings progress.
- Search transactions.
- Filter transactions.
- Analyze expenses.
- Export financial data.

The current version uses **HTML5, CSS3, JavaScript and Browser LocalStorage**.

---

# 3. Design Goals

The system design follows the following goals:

1. Simplicity
2. Usability
3. Maintainability
4. Reliability
5. Responsiveness
6. Modularity
7. Data consistency
8. Extensibility
9. Performance
10. Easy deployment

---

# 4. Design Principles

The following software design principles are followed:

## 4.1 Separation of Concerns

The project separates:

- Structure
- Presentation
- Application logic
- Data storage

```text
HTML  → Structure
CSS   → Presentation
JS    → Application Logic
Storage → Data Persistence
```

---

## 4.2 Modularity

Application functionality is divided into logical modules.

Examples:

- Dashboard Module
- Transaction Module
- Budget Module
- Savings Module
- Storage Module
- Export Module

---

## 4.3 Reusability

Common calculations and operations should be implemented using reusable JavaScript functions.

---

## 4.4 Maintainability

The system should be easy to understand and modify.

---

# 5. System Architecture

The application follows a client-side layered architecture.

```text
                    +----------------+
                    |      USER      |
                    +-------+--------+
                            |
                            v
                  +-------------------+
                  |    WEB BROWSER    |
                  +---------+---------+
                            |
                            v
             +-----------------------------+
             |      PRESENTATION LAYER     |
             |        HTML + CSS           |
             +-------------+---------------+
                           |
                           v
             +-----------------------------+
             |     APPLICATION LAYER       |
             |         JavaScript         |
             +-------------+---------------+
                           |
                           v
             +-----------------------------+
             |       DATA STORAGE LAYER    |
             |        LocalStorage         |
             +-----------------------------+
```

---

# 6. Architecture Layers

## 6.1 Presentation Layer

The presentation layer provides the user interface.

### Technologies

- HTML5
- CSS3

### Responsibilities

- Display dashboard
- Display forms
- Display transaction table
- Display budget progress
- Display savings progress
- Display expense analysis
- Provide responsive layout

---

# 6.2 Application Logic Layer

The application layer contains the main business logic.

### Technology

JavaScript ES6

### Responsibilities

- Input validation
- Transaction processing
- Financial calculations
- Budget calculation
- Savings calculation
- Search
- Filtering
- Dashboard updates
- CSV generation

---

# 6.3 Data Storage Layer

The current application uses Browser LocalStorage.

### Responsibilities

- Store transactions
- Store monthly budget
- Store savings goal
- Retrieve saved data
- Update stored data

---

# 7. High-Level System Architecture

```text
+------------------------------------------------+
|                  USER                          |
+-------------------------+----------------------+
                          |
                          v
+------------------------------------------------+
|             USER INTERFACE                     |
|                                                |
| Dashboard | Forms | Tables | Filters | Reports|
+-------------------------+----------------------+
                          |
                          v
+------------------------------------------------+
|             APPLICATION LOGIC                 |
|                                                |
| Transaction | Budget | Savings | Analysis     |
+-------------------------+----------------------+
                          |
                          v
+------------------------------------------------+
|                DATA STORAGE                    |
|                                                |
|                LocalStorage                   |
+------------------------------------------------+
```

---

# 8. System Modules

## 8.1 Dashboard Module

The Dashboard Module provides an overview of the user's financial condition.

### Inputs

- Income transactions
- Expense transactions
- Monthly budget
- Savings goal

### Outputs

- Total income
- Total expenses
- Current balance
- Savings rate
- Budget utilization
- Savings progress

---

# 8.2 Transaction Management Module

This module handles financial transactions.

### Operations

```text
Create
Read
Update
Delete
```

Therefore, it provides basic CRUD functionality.

### Transaction Types

- Income
- Expense

---

# 8.3 Budget Management Module

This module manages the monthly spending budget.

### Responsibilities

- Accept budget amount.
- Store budget.
- Calculate budget utilization.
- Display budget status.
- Identify budget overuse.

### Formula

```text
Budget Utilization =
(Total Expenses / Monthly Budget) × 100
```

---

# 8.4 Savings Goal Module

This module manages the user's savings target.

### Responsibilities

- Accept savings target.
- Store savings goal.
- Calculate progress.
- Display savings status.

### Formula

```text
Savings Progress =
(Current Balance / Savings Goal) × 100
```

---

# 8.5 Expense Analysis Module

This module groups expenses according to categories.

### Categories

- Food
- Transport
- Education
- Shopping
- Bills
- Entertainment
- Health
- Other

The module calculates the total amount spent in each category.

---

# 8.6 Search and Filter Module

This module allows users to locate specific transactions.

### Search

Users can search using:

- Description
- Category

### Filters

Users can filter by:

- Income
- Expense
- Category

---

# 8.7 Storage Module

The Storage Module manages LocalStorage.

### Main Operations

```text
Save Data
Load Data
Update Data
Delete Data
Clear Data
```

---

# 8.8 Export Module

The Export Module converts transaction records into CSV format.

### Process

```text
Transaction Data
       ↓
Generate CSV
       ↓
Create File
       ↓
Browser Download
```

---

# 9. Component Design

The main components are:

```text
Application
│
├── Header
│
├── Dashboard
│   ├── Income Card
│   ├── Expense Card
│   ├── Balance Card
│   └── Savings Rate Card
│
├── Budget Section
│
├── Savings Section
│
├── Transaction Form
│
├── Transaction Table
│
├── Search & Filter
│
└── Expense Analysis
```

---

# 10. Dashboard Component

The dashboard consists of four primary cards.

### Income Card

Displays total income.

### Expense Card

Displays total expenses.

### Balance Card

Displays:

```text
Income - Expenses
```

### Savings Rate Card

Displays:

```text
(Balance / Income) × 100
```

---

# 11. Transaction Component

The transaction component contains:

```text
Transaction Type
Description
Category
Amount
Date
Submit Button
```

The component validates the information before storing it.

---

# 12. Data Model

The application uses a simple transaction data structure.

```text
Transaction
--------------------------------
id
type
description
category
amount
date
```

Example:

```json
{
  "id": 101,
  "type": "expense",
  "description": "Groceries",
  "category": "Food",
  "amount": 2500,
  "date": "2026-10-08"
}
```

---

# 13. Application State

The complete application state can be represented as:

```json
{
  "transactions": [],
  "budget": 15000,
  "savingsGoal": 10000
}
```

The `transactions` array contains all financial records.

---

# 14. LocalStorage Design

The application stores the state under a predefined LocalStorage key.

Conceptually:

```text
LocalStorage
     |
     └── budgetPlanningApplication
              |
              ├── transactions
              ├── budget
              └── savingsGoal
```

---

# 15. Transaction Lifecycle

```text
User enters transaction
          ↓
Input validation
          ↓
Valid?
   ┌──────┴──────┐
   │             │
  No            Yes
   │             │
   v             v
Error Message   Save
                 |
                 v
            LocalStorage
                 |
                 v
          Update Dashboard
```

---

# 16. Add Transaction Flow

```text
Start
  ↓
Select Type
  ↓
Enter Description
  ↓
Select Category
  ↓
Enter Amount
  ↓
Select Date
  ↓
Validate Input
  ↓
Save Transaction
  ↓
Update LocalStorage
  ↓
Recalculate Dashboard
  ↓
Display Updated Data
```

---

# 17. Edit Transaction Flow

```text
Select Transaction
        ↓
Click Edit
        ↓
Load Existing Data
        ↓
Modify Information
        ↓
Validate
        ↓
Update Transaction
        ↓
Save Data
        ↓
Refresh Dashboard
```

---

# 18. Delete Transaction Flow

```text
Select Transaction
        ↓
Click Delete
        ↓
Confirmation
        ↓
User Confirms?
    /        \
  No          Yes
  |            |
  ↓            ↓
Cancel       Delete
               |
               ↓
        Update LocalStorage
               |
               ↓
        Refresh Dashboard
```

---

# 19. Budget Calculation Flow

```text
Get Total Expenses
        ↓
Get Monthly Budget
        ↓
Calculate Percentage
        ↓
Display Progress
        ↓
Check Budget Limit
        ↓
Display Warning if Required
```

---

# 20. Savings Calculation Flow

```text
Get Total Income
        ↓
Get Total Expenses
        ↓
Calculate Balance
        ↓
Get Savings Goal
        ↓
Calculate Progress
        ↓
Display Savings Status
```

---

# 21. Input Validation Design

All important user inputs should be validated.

## Transaction Validation

```text
Description ≠ Empty
Amount > 0
Date ≠ Empty
Category ≠ Empty
Type = Income or Expense
```

## Budget Validation

```text
Budget ≥ 0
```

## Savings Goal Validation

```text
Savings Goal ≥ 0
```

---

# 22. Error Handling

The application should provide clear messages for invalid operations.

Examples:

```text
"Please enter valid transaction details."
```

Other possible errors:

- Empty description
- Invalid amount
- Missing date
- Invalid budget
- Invalid savings goal

---

# 23. User Interface Design

The UI is designed around a dashboard layout.

```text
+------------------------------------------------+
|              APPLICATION HEADER                |
+------------------------------------------------+
| Income | Expenses | Balance | Savings Rate    |
+------------------------------------------------+
|          Monthly Budget | Savings Goal         |
+------------------------------------------------+
|              Add Transaction                  |
+------------------------------------------------+
| Search | Type Filter | Category Filter        |
+------------------------------------------------+
|              Transaction Table                |
+------------------------------------------------+
|             Expense Analysis                  |
+------------------------------------------------+
```

---

# 24. Responsive Design

The application should adapt its layout based on screen size.

### Desktop

Multiple dashboard cards are displayed in one row.

### Tablet

Cards and sections are reorganized into fewer columns.

### Mobile

Components are displayed vertically.

```text
Desktop
[Card][Card][Card][Card]

Tablet
[Card][Card]
[Card][Card]

Mobile
[Card]
[Card]
[Card]
[Card]
```

---

# 25. Data Flow Design

## Input

User provides:

- Transaction information
- Budget
- Savings goal

## Processing

JavaScript performs:

- Validation
- Calculations
- Filtering
- State updates

## Storage

Data is saved in LocalStorage.

## Output

The application displays:

- Financial summary
- Transactions
- Budget progress
- Savings progress
- Expense analysis

---

# 26. Security Design

The current application does not handle authentication or banking credentials.

Security considerations include:

- Validate user input.
- Avoid storing sensitive credentials.
- Avoid exposing unnecessary data.
- Prevent invalid financial values.

Future backend implementation should include:

- HTTPS
- Authentication
- Authorization
- Password hashing
- Secure APIs
- Database security

---

# 27. Performance Design

The application is designed for fast client-side operations.

Since calculations are performed in the browser:

- No server request is required.
- Dashboard updates are immediate.
- Search is performed locally.
- Filtering is performed locally.
- LocalStorage access is lightweight for normal usage.

---

# 28. Reliability Design

The system maintains a single application state.

After every major modification:

```text
Update State
     ↓
Save State
     ↓
Render UI
```

This approach keeps the interface synchronized with stored data.

---

# 29. Maintainability Design

The project uses a simple directory structure:

```text
Budget-Planning-Application/
│
├── README.md
├── SRS.md
│
├── docs/
│
├── src/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── tests/
│
└── screenshots/
```

The separation of files makes the system easier to modify.

---

# 30. Scalability Design

The current LocalStorage-based architecture can later be replaced with a backend.

### Current Architecture

```text
Frontend
   ↓
JavaScript
   ↓
LocalStorage
```

### Future Architecture

```text
Frontend
   ↓
REST API
   ↓
Backend Server
   ↓
Database
```

Possible backend technologies:

```text
Node.js + Express.js
```

Possible databases:

```text
MongoDB
PostgreSQL
MySQL
```

---

# 31. Future Cloud Architecture

A future version can follow:

```text
                  +-------------+
                  |    User     |
                  +------+------+
                         |
                         v
                  +-------------+
                  |  Frontend   |
                  +------+------+
                         |
                         v
                  +-------------+
                  | REST API    |
                  +------+------+
                         |
                         v
                  +-------------+
                  | Backend     |
                  | Node/Express|
                  +------+------+
                         |
                         v
                  +-------------+
                  |  Database   |
                  +-------------+
```

---

# 32. Deployment Design

The current application can be deployed as a static website.

Possible deployment platforms include:

- GitHub Pages
- Netlify
- Vercel

The application does not require a backend server in its current version.

---

# 33. Version Control Design

Git will be used for version control.

Recommended workflow:

```text
Development
     ↓
Git Add
     ↓
Git Commit
     ↓
Git Push
     ↓
GitHub Repository
```

Example:

```bash
git add .
git commit -m "Add budget planning application"
git push
```

---

# 34. Design Trade-offs

## LocalStorage

### Advantages

- Simple.
- No server required.
- Easy deployment.
- Fast for small datasets.

### Disadvantages

- Limited storage.
- Device-specific.
- No synchronization.
- No multi-user support.

Therefore, LocalStorage is appropriate for the initial academic prototype, while a database would be more appropriate for a production system.

---

# 35. Design Summary

The Budget Planning Application uses a lightweight client-side architecture consisting of:

```text
HTML
 ↓
CSS
 ↓
JavaScript
 ↓
LocalStorage
```

The architecture is intentionally simple to make the application:

- Easy to understand.
- Easy to develop.
- Easy to test.
- Easy to deploy.
- Easy to maintain.

The modular design also provides a clear path toward future backend and cloud integration.

---

# 36. Conclusion

The System Design of the **Budget Planning Application** translates the requirements defined in the SRS into a practical technical architecture.

The system separates presentation, application logic, and data storage responsibilities.

The modular design supports:

- Transaction management.
- Budget planning.
- Savings tracking.
- Expense analysis.
- Data persistence.
- Data export.
- Responsive UI.

The current architecture is suitable for a Software Engineering academic project and can be extended into a production-level application by introducing authentication, REST APIs, backend services, and a centralized database.

---

**Project:** Budget Planning Application  
**Developer:** Ansh Pandey  
**Document:** System Design Document  
**Version:** 1.0  
**Year:** 2026
