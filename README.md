📌 About the Project

**Budget Planning Application** is a personal finance management web application developed as a **Software Engineering project**.

The main purpose of this application is to help users manage their personal finances in an organized way. Users can record their income and expenses, define a monthly budget, set savings goals, and monitor their financial progress through an easy-to-use dashboard.

The application provides a simple alternative to maintaining financial records manually in notebooks or spreadsheets.

---

## 🎯 Problem Statement

Managing personal finances manually can make it difficult to understand where money is being spent and whether the monthly budget is being followed.

Users often face problems such as:

- Lack of proper expense tracking
- Difficulty maintaining a monthly budget
- No clear view of available balance
- Poor understanding of spending categories
- Difficulty tracking savings progress
- Manual calculation of income and expenses

The **Budget Planning Application** addresses these problems by providing a centralized platform for managing and monitoring personal finances.

---

## 🎯 Objectives

The major objectives of this project are:

- To provide an easy-to-use budget management system.
- To record and organize income and expenses.
- To calculate total income, expenses and remaining balance automatically.
- To help users set and monitor monthly budgets.
- To provide savings goal tracking.
- To analyze expenses according to categories.
- To reduce manual financial calculations.
- To provide a responsive and user-friendly interface.
- To maintain financial data using browser LocalStorage.

---

## ✨ Features

### 💵 Income Management

- Add income transactions
- Edit income records
- Delete income records
- Categorize income
- Automatically calculate total income

### 💸 Expense Management

- Add expenses
- Edit expenses
- Delete expenses
- Categorize expenses
- Automatically calculate total expenses

### 📊 Dashboard

The dashboard provides an overview of:

- Total Income
- Total Expenses
- Current Balance
- Savings Rate
- Monthly Budget
- Budget Usage
- Savings Goal
- Savings Progress

### 🎯 Budget Planning

Users can define a monthly spending budget.

The application automatically calculates:

```text
Budget Used = Total Expenses / Monthly Budget × 100
```

If expenses exceed the planned budget, the application provides a budget warning.

### 🏦 Savings Goal

Users can define a savings target and monitor their progress.

Example:

```text
Savings Goal = ₹20,000
Current Balance = ₹12,000

Progress = 60%
```

### 📂 Category Analysis

Expenses can be categorized into:

- Food
- Transport
- Education
- Shopping
- Bills
- Entertainment
- Health
- Other

The application displays category-wise spending to help users understand their spending habits.

### 🔎 Search & Filter

Users can:

- Search transactions
- Filter by Income/Expense
- Filter by Category

### 💾 Data Persistence

Application data is stored using **Browser LocalStorage**, so data remains available even after refreshing the page.

### 📥 CSV Export

Users can export their transaction records into a CSV file for backup or further analysis.

### 📱 Responsive Design

The application is designed to work on:

- Desktop
- Laptop
- Tablet
- Mobile devices

---

# 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| CSS3 | Styling and responsive design |
| JavaScript ES6 | Application logic |
| LocalStorage | Client-side data persistence |
| CSV | Transaction data export |

---

# 🏗️ System Architecture

The application follows a simple client-side architecture.

```text
                ┌─────────────────────┐
                │        User         │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │     Web Interface   │
                │     HTML + CSS       │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Application Logic │
                │     JavaScript      │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │    LocalStorage     │
                │   Browser Storage   │
                └─────────────────────┘
```

---

# 📁 Project Structure

```text
Budget-Planning-Application/
│
├── README.md
├── SRS.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── Software-Requirements.md
│   ├── System-Design.md
│   ├── Use-Case.md
│   ├── Test-Plan.md
│   └── User-Manual.md
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

# ⚙️ Installation & Setup

## Step 1 — Clone the Repository

```bash
git clone https://github.com/mahiansh11/Budget-Planning-Application.git
```

## Step 2 — Open the Project

```bash
cd Budget-Planning-Application
```

## Step 3 — Run the Application

Open:

```text
src/index.html
```

in any modern web browser.

### Recommended

If you are using **VS Code**, install the **Live Server** extension and open the project using Live Server.

---

# 🚀 How to Use

### 1. Add Income

Select:

```text
Income → Description → Category → Amount → Date
```

Then click:

```text
Add Transaction
```

### 2. Add Expense

Select:

```text
Expense → Description → Category → Amount → Date
```

Then click:

```text
Add Transaction
```

### 3. Set Monthly Budget

Enter your desired monthly budget and click:

```text
Save Budget
```

### 4. Set Savings Goal

Enter the desired savings amount and click:

```text
Save Goal
```

### 5. Manage Transactions

Every transaction can be:

- Edited
- Deleted
- Searched
- Filtered

### 6. Export Data

Click:

```text
Export CSV
```

to download transaction records.

---

# 🧮 Financial Calculations

### Total Income

```text
Total Income = Sum of all income transactions
```

### Total Expenses

```text
Total Expenses = Sum of all expense transactions
```

### Current Balance

```text
Balance = Total Income - Total Expenses
```

### Savings Rate

```text
Savings Rate = (Balance / Total Income) × 100
```

### Budget Utilization

```text
Budget Utilization =
(Total Expenses / Monthly Budget) × 100
```

---

# 🧩 Main Modules

## 1. Dashboard Module

Displays the user's overall financial status.

## 2. Transaction Management Module

Responsible for:

- Creating transactions
- Updating transactions
- Deleting transactions
- Searching transactions
- Filtering transactions

## 3. Budget Management Module

Responsible for setting and monitoring the monthly budget.

## 4. Savings Goal Module

Responsible for setting and tracking savings targets.

## 5. Expense Analysis Module

Provides category-wise expense analysis.

## 6. Storage Module

Stores application data using browser LocalStorage.

## 7. Export Module

Converts transaction data into CSV format.

---

# 🧪 Testing

The project includes a dedicated testing document containing test cases for:

- Adding transactions
- Editing transactions
- Deleting transactions
- Input validation
- Budget calculation
- Savings calculation
- Search functionality
- Filtering
- LocalStorage persistence
- CSV export
- Responsive UI

Detailed test cases are available in:

```text
tests/test-cases.md
```

---

# 📚 Software Engineering Documentation

This project has been designed according to Software Engineering principles.

The repository contains:

| Document | Description |
|---|---|
| `SRS.md` | Software Requirements Specification |
| `Software-Requirements.md` | Functional & Non-Functional Requirements |
| `System-Design.md` | System Architecture & Module Design |
| `Use-Case.md` | Use Cases and User Interactions |
| `Test-Plan.md` | Testing Strategy |
| `test-cases.md` | Detailed Test Cases |
| `User-Manual.md` | Application Usage Guide |

---

# 🔐 Data & Privacy

The current version uses browser **LocalStorage**.

This means:

- Data is stored locally on the user's device.
- No financial data is sent to a server.
- No banking credentials are collected.
- Clearing browser site data may remove stored transactions.

Users can use the **CSV Export** feature to maintain a backup.

---

# 🔮 Future Scope

The application can be extended with:

- 🔐 User authentication
- ☁️ Cloud database
- 👥 Multiple user accounts
- 🔄 Recurring transactions
- 📅 Monthly/yearly financial reports
- 📄 PDF report generation
- 📊 Advanced charts and analytics
- 🤖 AI-based spending recommendations
- 🏦 Bank account integration
- 📱 Android/iOS mobile application
- 🔔 Budget and payment notifications

---

# ⚠️ Current Limitations

- Data is stored only in browser LocalStorage.
- There is no user authentication.
- Data is not synchronized across devices.
- The application does not connect to real bank accounts.
- Clearing browser storage can remove application data.

---

# 👨‍💻 Software Engineering Concepts Used

This project demonstrates several Software Engineering concepts:

- Requirement Engineering
- Functional Requirements
- Non-Functional Requirements
- Software Architecture
- Modular Design
- User-Centered Design
- Validation
- Testing
- Risk Analysis
- Maintainability
- Usability
- Future Scalability

---

# 📈 Project Workflow

```text
Requirement Analysis
        ↓
System Design
        ↓
UI Design
        ↓
Implementation
        ↓
Testing
        ↓
Debugging
        ↓
Documentation
        ↓
Final Deployment
```

---

# 🤝 Contribution

Contributions are welcome.

To contribute:

```bash
git fork
git clone
git checkout -b feature-name
git commit -m "Add new feature"
git push
```

Then create a Pull Request.

---

# 📄 License

This project is licensed under the **MIT License**.

---

# 👨‍🎓 Author

**Abhishek Tiwari**

**B.Tech Computer Science & Engineering**

---

## ⭐ Project Summary

The **Budget Planning Application** provides a simple and effective solution for personal financial planning. It combines budget management, expense tracking, savings goals and financial analysis into a single responsive web application.

The project also demonstrates the complete Software Engineering development process, from **requirements analysis and system design to implementation, testing and documentation**.

> **Plan your money. Track your spending. Achieve your goals. 💰**
