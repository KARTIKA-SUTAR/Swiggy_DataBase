# 🍔 Swiggy Food Delivery Management System – SQL Project

A MySQL project that models a **Swiggy-style food delivery platform** and solves **150 practice questions**, from basic `SELECT` queries to window functions, CTEs, and business KPI reports.

## 📌 Project Overview

This project covers the full workflow of a SQL database project:

1. **Database design** – 9 related tables with primary keys, foreign keys, constraints, and indexes
2. **Sample data** – realistic data for customers, restaurants, orders, deliveries, payments, and reviews across South Indian cities
3. **Query practice** – 150 questions grouped into 5 levels of difficulty
4. **Business analysis** – revenue, customer lifetime value, delivery performance, and executive reports

---

## 📂 Repository Structure

```
├── Swiggy.sql                  # Schema + sample data + solutions to all 150 questions
├── Questions.pdf               # SQL practice workbook (150 questions)
└── README.md                   # Project documentation
```

---

## 🗄️ Database Schema

**Database name:** `SwiggyDB`

| Table | Description | Rows |
|---|---|---|
| `Customers` | Customer profile, city, area, registration date | 100 |
| `Restaurants` | Restaurant name, cuisine, city, rating, timings | 20 |
| `MenuCategories` | Breakfast, Lunch, Dinner, Snacks, etc. | 8 |
| `MenuItems` | Items per restaurant with price, veg/non-veg flag, availability | 120 |
| `Orders` | Order date, status, delivery address, total amount | 298 |
| `DeliveryPartners` | Partner details, vehicle type, rating, status | 25 |
| `Delivery` | Assigned / pickup / delivery times, status, delivery rating | 298 |
| `Payments` | Payment method, status, amount, transaction ID | 298 |
| `Reviews` | Food rating, delivery rating, review comment | 100 |

### Table Relationships

```
Customers ──< Orders >── Restaurants ──< MenuItems >── MenuCategories
                │
                ├──── 1:1 ──── Payments
                ├──── 1:1 ──── Delivery >── DeliveryPartners
                └──── 1:1 ──── Reviews
```

### Key Design Features

- **Primary keys** with `AUTO_INCREMENT` on all tables
- **Foreign keys** to maintain referential integrity
- **`ENUM`** columns for controlled values (order status, payment method, payment status, gender, vehicle type)
- **`UNIQUE`** constraints on mobile number, email, and one-to-one order relations
- **`CHECK`** constraints on ratings (1–5)
- **Indexes** on `Customers(City)`, `Restaurants(City)`, `Orders(OrderDate)`, and `Delivery(DeliveryTime)`

---

## 📝 Question Breakdown

| Part | Topic | Questions | Skills Covered |
|---|---|---|---|
| **A** | Beginner SQL | 1 – 40 | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, `DISTINCT`, `LIKE`, `IN`, `BETWEEN`, `IS NULL`, aliases |
| **B** | Aggregate Functions | 41 – 60 | `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, `ROUND`, `GROUP BY`, `HAVING` |
| **C** | JOIN Queries | 61 – 90 | `INNER JOIN`, `LEFT JOIN`, multi-table joins, joins with aggregation, consolidated reports |
| **D** | Date Functions | 91 – 120 | `CURDATE`, `NOW`, `YEAR`, `MONTH`, `DAYNAME`, `DATEDIFF`, `TIMESTAMPDIFF`, `DATE_ADD`, `DATE_FORMAT`, monthly summaries |
| **E** | Advanced SQL | 121 – 150 | Window functions, CTEs, subqueries, `CASE`, conditional aggregation, CLV, KPI dashboards |

### Advanced Concepts Used

- **Window functions:** `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `NTILE()`, `LAG()`, `LEAD()`, running totals, moving averages
- **Common Table Expressions (CTEs)** for readable, modular queries
- **Subqueries** (correlated and non-correlated)
- **Conditional logic** with `CASE` statements
- **Set-style filtering** with `EXISTS` / `NOT EXISTS` / `LEFT JOIN ... IS NULL`

---

## 📊 Business Insights You Can Derive

- Total revenue and revenue by payment method
- Top-performing restaurants and top customers by lifetime spending
- Customer Lifetime Value (CLV)
- Monthly, daily, weekday-wise, and hour-wise order trends
- Delivery partner performance (average delivery time, deliveries handled)
- Restaurant ratings and revenue contribution (%)
- Executive report combining orders, revenue, ratings, and delivery time

---

## 🧰 Tech Stack

- **Database:** MySQL 8.0+
- **Language:** SQL
- **Tools:** MySQL Workbench / DBeaver / VS Code

---

## 🎯 Learning Outcomes

After working through this project you will be able to:

- Design a normalized relational database with proper constraints
- Write filtering, sorting, and pattern-matching queries
- Summarize data using aggregate functions and `GROUP BY`
- Combine multiple tables with different types of joins
- Analyze time-based data using date and time functions
- Use window functions and CTEs for advanced analytics
- Build KPI dashboards and executive-level reports with SQL
