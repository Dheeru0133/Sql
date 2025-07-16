# 🧠 Sales Insights Project — SQL + Power BI

This project showcases a complete data analysis workflow built using **SQL for querying** and **Power BI for visualization**.

The dataset represents an E-commerce business. I used SQL to explore, clean, and join the data. Then, I exported query results as CSVs and built an interactive Power BI dashboard using relationships, DAX measures, and visuals.

---

## 🛠 Tools & Skills Used

- 🗃️ MySQL – querying, filtering, joins, aggregations
- 📊 Power BI – data modeling, DAX, dashboard design
- 📂 CSV Exports – output from SQL used in Power BI
- 🧠 Concepts – PK/FK, GROUP BY, CASE, DATE functions, DAX, KPIs

---

## 📁 Project Flow

### 🔹 Step 1 – SQL (Data Preparation)
- Queried tables: `Orders`, `OrderDetails`, `Customers`, `Products`, `Regions`
- Calculated revenue, returns, top products, regional sales, etc.
- Exported 5 result tables as CSVs

### 🔹 Step 2 – Power BI (Dashboarding)
- Imported the CSVs into Power BI
- Created model with 1-to-many relationships
- Built DAX measures for key KPIs
- Designed a clean, insightful dashboard

---

## 📊 Dashboard Elements

### ✅ KPI Cards:
- 💰 Total Revenue  
- 📦 Total Orders  
- 🔁 Return Rate  

### ✅ Visuals:
1. 📈 **Line Chart** – Total Revenue by Order Year  
2. 📊 **Bar Chart** – Top 10 Products by Revenue  
3. 🏙 **Column Chart** – Revenue by Region Name  
4. 🧺 **Column Chart** – Revenue by Product Category  

---

## 🧮 Key DAX Measures

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
```

---

## 📸 Dashboard Screenshot

> Save your dashboard screenshot as:  
> 📂 `Images/dashboard.png`  

Then it will display here:

![Power BI Dashboard](Images/dashboard.png)

---

## 🚀 How to Use

1. Clone/download this repository  
2. Open `SalesDashboard.pbix` in Power BI Desktop  
3. Explore visuals and interact with slicers/tooltips  

---

## 👨‍💻 Built By

**Dheeru**  
B.Tech CSE  
SQL + Power BI Portfolio Project  
Full pipeline: Query ➜ Clean ➜ Export ➜ Visualize  

---

## 📝 Notes

- All logic and joins were written in SQL first  
- Dashboard was built from exported SQL outputs (CSV)  
- Project reflects real-world analyst flow: from raw data to visual insights
