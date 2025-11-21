# Power-BI-Sales-Analytics-Dashboard
*A refined, data-driven analysis of global sales performance for the Awesome Chocolate Company.*

---

## 📍 Overview  
This dashboard presents a high-level yet detailed view of sales performance across regions, product categories, and sales personnel. The design focuses on clarity, structured storytelling, and business relevance—avoiding unnecessary noise and emphasizing insight over decoration.

---

## 🎯 Objectives  
- Understand overall business performance using key KPIs  
- Identify high-performing regions, products, and sales executives  
- Evaluate shipment volumes, cost structures, and profitability  
- Provide decision-ready insights for leadership and operations teams  

---

## 🧮 Key Metrics  
The report highlights the following KPIs:

- **Total Sales:** $34M  
- **Total Boxes Sold:** 2M  
- **Total Shipments:** 6K  
- **Total Cost:** $13.52M  
- **Total Profit:** $21M  
- **Profit %:** 60.3%

These indicators set the foundation for examining the company’s operational efficiency and financial health.

---

## 🔍 Insights & Analysis  

### **1. Sales & Profitability Trends**  
Line charts depict month-over-month movement in:  
- Total Sales  
- Total Cost  
- Profit %  
- Shipments  
- Boxes Sold  

The company maintains healthy profit margins (~60%) throughout the period, with consistent demand across most months.

---

### **2. Salesperson Performance**  
A ranked table showcases:  
- Individual Sales  
- Profit Contribution  
- Profitability %  
- LBS% (Logistics efficiency indicator)  

Top performers—such as Brien Boise and Camilla Castle—demonstrate both high revenue and strong margin contribution.

---

### **3. Regional Shipment Volume**  
A histogram displays shipment distribution by box volume, helping identify:  
- High-frequency shipment ranges  
- Operational bottlenecks  
- Logistic efficiency shifts over time  

---

### **4. Segment Navigation**  
The left-panel navigation allows quick access to category-level performance:  
- Bars  
- Bites  
- Other  
- Country-based segmentation (India, USA, UK, Australia, etc.)

This adds flexibility and allows deeper drilldowns without cluttering the main view.

---

## 🛠 Tools Used  
- **Power BI Desktop** – Data modeling, DAX, and report design  
- **Excel/CSV** – Dataset preparation  
- **DAX Measures** – KPI calculations & trend modeling  
- **Power Query** – Data cleaning & transformation  

---

## 🧪 Data Cleaning Process  
The following steps were applied using Power Query:

- Removed duplicates & null entries  
- Standardized date formats  
- Normalized product & region labels  
- Built calculated columns for profit, cost ratios, and logistics %  
- Established a clean star-schema structure for optimal performance  

---

## 🧮 Sample DAX Measures  

```DAX
Total Sales :=
SUM(shipments[Sales])

Total Cost := 
SUM(shipments[Costs])

Total Profit :=
[Total Sales]-[Total Cost]

Total Shipments := 
COUNTROWS(shipments)

Profit % :=
DIVIDE([Total Profit],[Total Sales])

LBS Count := 
CALCULATE([Total Shipments], shipments[Boxes]<50)

LBS % :=
DIVIDE([LBS Count], [Total Shipments])
