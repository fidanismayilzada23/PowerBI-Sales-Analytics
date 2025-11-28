# 🍔 Fast Food Sales Analytics Dashboard – Power BI

This project presents an end-to-end **Sales Analytics Dashboard** developed in **Power BI** using real fast-food sales data.  
The goal is to analyze **customer purchasing behavior, peak sale timings, transaction types and monthly growth trend** to support data-driven business decisions.

---

## 📊 Key Insights

🔹 Monthly sales demonstrate a continuous upward trend, especially during winter months  
🔹 Evening and late-night hours generate the highest volume of orders  
🔹 Cash payments represent the majority of total transactions compared to card payments**  
🔹 Male customers purchase higher quantities on average than female customers  
🔹 Sandwich is the most consistently high-performing item throughout the year**  

---

## 🧠 Analytical Focus
The dashboard answers the following business questions:

| Question | Metric / Measure |
|---------|------------------|
| Which months perform best? | Total Sales & MoM Growth |
| What time of the day drives the highest revenue? | Sales by Time of Day |
| Which customer segment buys more? | Sales by Gender & Quantity |
| Which payment method is more preferred? | Sales by Transaction Type |
| Which item contributes the most to yearly sales? | Item-Level Performance |

---

## 🛠 Tech Stack
- **Power BI**
- **DAX (Time Intelligence & Aggregation Measures)**
- **Power Query (Data Cleaning & Transformation)**
- **Excel / CSV Dataset**

---

## 📁 Project Structure
/dataset → Raw CSV
/dashboards → Power BI (.pbix) file
/exports → Dashboard PDF & preview images
/dax_measures → DAX formulas used in the project
README.md → You are here

---

## 🧮 DAX Measures (Examples)

```DAX
Total Sales = SUM('Table'[transaction_amount])

MoM Growth =
VAR CurrentMonth = [Total Sales]
VAR PreviousMonth =
    CALCULATE(
        [Total Sales],
        DATEADD('Table'[date], -1, MONTH)
    )
RETURN
DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth)

Sales by Gender = SUM('Table'[transaction_amount])

Sales by Payment Method = SUM('Table'[transaction_amount])

Sales by Item = SUM('Table'[transaction_amount])
All measures used in the project are included in /dax_measures/DAX_Measures.txt


