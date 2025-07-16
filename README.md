# 🧠 Sales Insights Project — SQL + Power BI

This project showcases a full data analysis pipeline built using **SQL for data querying** and **Power BI for dashboarding**.

The data is based on an E-commerce sales system. First, I used SQL to clean, join, and extract insights from raw tables. Then, I exported those query results to CSVs and built a fully interactive dashboard in Power BI using **data modeling**, **DAX**, and visuals.

---

## 🛠 Tools & Skills Used

- 🗃️ MySQL (data analysis, joins, filtering, aggregations)
- 📊 Power BI (dashboard design, DAX, slicers, tooltips)
- 📂 CSV Exports (SQL output imported to Power BI)
- 📚 Skills: Joins, Group By, CASE, DATE functions, Measures, Data Modeling

---

## 📁 Data Flow (How I Built It)

1. **Step 1 — SQL Work (in MySQL):**
   - Queried tables: `Orders`, `OrderDetails`, `Customers`, `Products`, `Regions`
   - Wrote SQL to calculate:
     - Revenue per order
     - Returned orders
     - Top-selling products
     - Regional sales
   - Exported query outputs as **5 CSV files**

2. **Step 2 — Power BI Dashboarding:**
   - Imported CSVs into Power BI
   - Created relationships (1-to-many) across tables
   - Built DAX Measures: `Total Revenue`, `Return Rate`, etc.
   - Designed a multi-visual dashboard

---

## 📊 Dashboard Features

### ✅ KPI Cards:
- 💰 Total Revenue
- 📦 Total Orders
- 🔁 Return Rate

### ✅ Visuals:
- 📈 Line Chart → Revenue by Year
- 📊 Bar Chart → Top 10 Products by Revenue
- 🗺 Column Chart → Revenue by Region
- 🧺 Column Chart → Revenue by Product Category
- 🎯 Comparison Chart → Actual vs Target Revenue (110%)

---

## 🧮 Key DAX Measures (Power BI Side)

```DAX
-- Total Revenue
Total Revenue = 
SUMX(OrderDetails, OrderDetails[Quantity] * RELATED(Products[Price]))

-- Returned Orders
Returned Orders = 
CALCULATE(COUNTROWS(Orders), Orders[IsReturned] = 1)

-- Return Rate
Return Rate = 
DIVIDE([Returned Orders], COUNTROWS(Orders), 0)

-- Previous Month Revenue
Previous Month Revenue = 
CALCULATE(
    [Total Revenue],
    DATESINPERIOD(
        Orders[OrderDate],
        EOMONTH(MAX(Orders[OrderDate]), -1),
        1,
        MONTH
    )
)

-- Target Revenue (110% of previous month)
Target Revenue = 
[Previous Month Revenue] * 1.1
```

---

## 📸 Dashboard Screenshot

👉 Add your full dashboard screenshot in the `Images` folder with the name:
```
Images/dashboard.png
```

Then it will appear here automatically:

![Power BI Dashboard](Images/dashboard.png)

---

## 🚀 How to Use

1. Clone/download this repo
2. Open `SalesDashboard.pbix` in Power BI Desktop
3. Explore insights using slicers and tooltips

---

## 👨‍💻 Built By

**Dheeru**  
B.Tech CSE  
SQL + Power BI End-to-End Project  
Built from scratch using real SQL logic and modern BI tools

---

## 📝 Notes

- SQL was used for all core calculations and aggregations
- Power BI used for modeling, visuals, and DAX enhancements
- Together this shows strong capability in **data querying and storytelling**
