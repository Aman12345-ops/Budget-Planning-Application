## 🌟 Overview

**Budget Planning Application** is a modern client-side web application designed to help users manage their personal finances in a simple and organized way.

With this application, users can:

💵 Track income  
💸 Manage expenses  
📊 Monitor monthly budgets  
🎯 Set savings goals  
🔎 Search and filter transactions  
📈 Analyse spending by category  
💾 Store data using LocalStorage  
📥 Export transactions as CSV  
📱 Use the application on desktop, tablet and mobile devices  

The project is developed as a **Software Engineering academic project** and demonstrates the complete software development lifecycle from requirements analysis to implementation and testing.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 💰 Income Management | Add, edit and delete income records |
| 💸 Expense Management | Track and manage daily expenses |
| 📊 Dashboard | View important financial information at a glance |
| 🎯 Budget Planning | Set and monitor monthly spending limits |
| 🏆 Savings Goals | Set savings targets and track progress |
| 🗂️ Category Analysis | Analyse expenses category-wise |
| 🔎 Search | Quickly search transactions |
| 🔽 Filter | Filter income and expense records |
| 💾 LocalStorage | Automatically preserve data in browser |
| 📥 CSV Export | Export transactions to a CSV file |
| 🔄 Reset Demo | Restore sample/demo data |
| 📱 Responsive UI | Works across different screen sizes |

---

# 🖥️ Application Preview

### 📊 Dashboard

> Add your screenshot here:

```text
screenshots/dashboard.png
```

![Dashboard](screenshots/dashboard.png)

### 💳 Transaction Management

![Transactions](screenshots/transactions.png)

### 📱 Responsive Design

![Mobile View](screenshots/mobile-view.png)

> 💡 **Tip:** Put your actual screenshots inside the `screenshots/` folder using the filenames above.

---

# 🛠️ Tech Stack

### 🎨 Frontend

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

### 💾 Storage

![LocalStorage](https://img.shields.io/badge/Browser-LocalStorage-orange?style=flat-square)

### 🔧 Development Tools

![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)

---

# 🏗️ System Architecture

The application follows a simple **client-side layered architecture**:

```text
                    👤 USER
                      │
                      ▼
        ┌─────────────────────────┐
        │     🎨 Presentation     │
        │      HTML + CSS         │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │    ⚙️ Application Logic │
        │       JavaScript        │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │      💾 Data Layer      │
        │       LocalStorage      │
        └─────────────────────────┘
```

---

# 📂 Project Structure

```text
Budget-Planning-Application/
│
├── 📄 README.md
├── 📄 SRS.md
├── 📄 LICENSE
├── 📄 .gitignore
│
├── 📁 docs/
│   ├── 📄 01-System-Design.md
│   ├── 📄 02-Use-Case-Diagram.md
│   ├── 📄 03-DFD.md
│   ├── 📄 04-ER-Diagram.md
│   ├── 📄 05-Flowchart.md
│   ├── 📄 06-Database-Design.md
│   ├── 📄 07-Test-Plan.md
│   └── 📄 08-User-Manual.md
│
├── 📁 src/
│   ├── 🌐 index.html
│   ├── 🎨 style.css
│   └── ⚙️ script.js
│
├── 📁 tests/
│   └── 🧪 test-cases.md
│
└── 📁 screenshots/
    ├── 🖼️ dashboard.png
    ├── 🖼️ transactions.png
    ├── 🖼️ budget.png
    └── 🖼️ mobile-view.png
```

---

# 🚀 Getting Started

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/Budget-Planning-Application.git
```

## 2️⃣ Navigate to the Project

```bash
cd Budget-Planning-Application
```

## 3️⃣ Run the Application

No backend or package installation is required.

Simply open:

```text
src/index.html
```

in your browser.

### 💡 Recommended

If you are using **VS Code**, install the **Live Server** extension and open the project using Live Server.

---

# 💡 How It Works

The application follows a simple financial workflow:

```text
👤 User
   │
   ├── 💰 Add Income
   │
   ├── 💸 Add Expense
   │
   ├── 📊 Set Budget
   │
   ├── 🎯 Set Savings Goal
   │
   ├── 🔎 Search / Filter
   │
   └── 📈 Analyse Finances
             │
             ▼
      💾 LocalStorage
```

---

# 🧮 Financial Calculations

### 💰 Total Income

```text
Total Income = Sum of all Income Transactions
```

### 💸 Total Expenses

```text
Total Expenses = Sum of all Expense Transactions
```

### 💵 Available Balance

```text
Balance = Total Income − Total Expenses
```

### 📊 Budget Usage

```text
Budget Usage (%) =
(Total Expenses / Monthly Budget) × 100
```

### 🎯 Savings

```text
Savings = Total Income − Total Expenses
```

### 🏆 Savings Progress

```text
Savings Progress (%) =
(Savings / Savings Goal) × 100
```

---

# 💾 Data Storage

The application uses the browser's **LocalStorage API** for persistence.

### Storage Key

```text
budgetPlanningApplication
```

### Example Data

```json
{
  "transactions": [
    {
      "id": 1,
      "type": "expense",
      "description": "Groceries",
      "category": "Food",
      "amount": 3500,
      "date": "2026-10-01"
    }
  ],
  "budget": 15000,
  "savingsGoal": 10000
}
```

> 🔐 No external server or database is required in the current version.

---

# 🧪 Testing

The project includes structured testing documentation covering:

✅ Functional Testing  
✅ CRUD Testing  
✅ Input Validation  
✅ Calculation Testing  
✅ LocalStorage Testing  
✅ Search & Filter Testing  
✅ Budget Testing  
✅ Savings Testing  
✅ CSV Export Testing  
✅ Reset Testing  
✅ Responsive UI Testing  
✅ Browser Compatibility Testing  

### 📋 Test Documentation

👉 [View Test Plan](docs/07-Test-Plan.md)

👉 [View Test Cases](tests/test-cases.md)

---

# 📚 Software Engineering Documentation

This project includes complete Software Engineering documentation.

| 📄 Document | 🔗 Link |
|---|---|
| 📋 Software Requirements Specification | [SRS](SRS.md) |
| 🏗️ System Design | [System Design](docs/01-System-Design.md) |
| 👤 Use Case Diagram | [Use Case Diagram](docs/02-Use-Case-Diagram.md) |
| 🔄 Data Flow Diagram | [DFD](docs/03-DFD.md) |
| 🗃️ ER Diagram | [ER Diagram](docs/04-ER-Diagram.md) |
| 🔀 Flowchart | [Flowchart](docs/05-Flowchart.md) |
| 💾 Database Design | [Database Design](docs/06-Database-Design.md) |
| 🧪 Test Plan | [Test Plan](docs/07-Test-Plan.md) |
| 📖 User Manual | [User Manual](docs/08-User-Manual.md) |
| 🧪 Test Cases | [Test Cases](tests/test-cases.md) |

---

# 🎯 Project Objectives

The project aims to:

- 🧾 Simplify personal expense tracking
- 💰 Manage income and expenses
- 📊 Monitor monthly budgets
- 🎯 Track savings goals
- 📈 Understand spending patterns
- 🔎 Find transactions quickly
- 💾 Maintain persistent browser data
- 📥 Provide downloadable financial records
- 📱 Provide a responsive user experience

---

# 🔐 Privacy & Security

The current version is a **client-side application**.

Therefore:

- 🔒 Data remains in the user's browser.
- 🌐 No financial information is sent to a remote server.
- 👤 No user account is required.
- ☁️ No cloud synchronization is currently implemented.

> ⚠️ This project is intended for educational and demonstration purposes. Users should avoid storing highly sensitive financial information in the application.

---

# ⚠️ Current Limitations

The current version does not include:

- ❌ User authentication
- ❌ Backend API
- ❌ Cloud database
- ❌ Multi-user support
- ❌ Cross-device synchronization
- ❌ Bank account integration
- ❌ Automated financial notifications

---

# 🚀 Future Scope

The application can be extended into a full-stack financial management platform.

### 🔮 Planned Improvements

- 🔐 User authentication
- ☁️ Cloud synchronization
- 🗄️ MongoDB/PostgreSQL database
- ⚙️ Node.js + Express backend
- 📊 Advanced charts and analytics
- 📄 PDF financial reports
- 🔔 Budget alerts
- 🔁 Recurring transactions
- 📱 Dedicated mobile application
- 🤖 AI-based spending recommendations
- 🌍 Multi-currency support
- 👥 Multi-user accounts

---

# 🧑‍💻 Software Engineering Concepts

This project demonstrates:

```text
📋 Requirement Engineering
        ↓
📄 SRS
        ↓
🏗️ System Design
        ↓
👤 Use Case Modelling
        ↓
🔄 DFD
        ↓
🗃️ ER Modelling
        ↓
🔀 Flowchart
        ↓
💻 Implementation
        ↓
🧪 Testing
        ↓
📖 Documentation
        ↓
🚀 Deployment
```

---

# 📈 Project Status

```text
████████████████████████████████ 100%
```

### ✅ Completed

- [x] Requirements Analysis
- [x] SRS
- [x] System Design
- [x] Use Case Diagram
- [x] DFD
- [x] ER Diagram
- [x] Flowcharts
- [x] Database Design
- [x] Application Development
- [x] Testing
- [x] Test Cases
- [x] User Manual
- [x] GitHub Documentation

---

# 👨‍💻 Author

## Ansh Pandey

🎓 **B.Tech — Computer Science & Engineering**

💻 **Software Engineering Project**

📅 **2026**

---

# ⭐ Support

If you find this project useful or interesting:

⭐ **Star the repository**

🍴 **Fork the repository**

📢 **Share the project**

---

# 📜 License

This project is developed for **academic and educational purposes**.

See the [LICENSE](LICENSE) file for more information.

---

<div align="center">

### 💰 Budget Planning Application

**Plan Better • Spend Smarter • Save More 🚀**

Made with ❤️ using **HTML, CSS & JavaScript**

⭐ **If you like this project, don't forget to star the repository!** ⭐

</div>
