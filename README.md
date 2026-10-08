
# Flipkart Sales Analytics Dashboard | Power BI

<img width="1435" height="786" alt="Screenshot 2026-10-07 184729" src="https://github.com/user-attachments/assets/930a06a3-f30a-42dd-8f8f-4aaf4643e459" />


## 📌 Project Overview
This project is an end-to-end data analysis and visualization project built using **Microsoft Power BI**. The goal was to analyze Flipkart's sales data to uncover insights regarding revenue, profitability, customer purchasing behavior, and geographic distribution. 

The dashboard provides a 360-degree view of the business, allowing stakeholders to filter by time (Quarterly buttons) and drill down into specific categories, sub-categories, and payment modes.

## 🛠️ Tech Stack & Skills Demonstrated
*   **Tool:** Microsoft Power BI Desktop
*   **Data Transformation:** Power Query (ETL)
*   **Data Modeling:** Star Schema (Fact and Dimension tables)
*   **Calculations:** DAX (Data Analysis Expressions)
*   **Visualization:** KPI Cards, Donut Charts, Bar Charts, Map Visuals, Slicers

## 📂 Dataset Information
The project utilizes two primary datasets (CSV format):
1.  **`Flipkart_details.csv` (Fact Table):** Contains transactional data including `Order ID`, `Amount`, `Profit`, `Quantity`, `Category`, `Sub_Category`, and `PaymentMode`.
2.  **`Flipkart_orders.csv` (Dimension Table):** Contains order-level information including `Order ID`, `Order Date`, `CustomerName`, `State`, and `City`.

## 🧹 Data Cleaning & Preparation (Power Query)
Before building the dashboard, the raw data was cleaned and transformed:
*   **Nulls & Errors:** Checked for empty values and errors using Column Quality and Column Profile.
*   **Data Types:** Corrected data types (e.g., ensuring `Order Date` is a Date format and `Amount` is Decimal).
*   **Text Cleaning:** Fixed trailing spaces in the `State` column (e.g., "Kerala " was trimmed to "Kerala") and standardized spelling (e.g., "Hankerchief" to "Handkerchief").
*   **Date Table:** Created a dedicated `DateTable` using DAX to enable accurate time-intelligence and quarterly filtering.

## 🗂️ Data Modeling
A **Star Schema** was implemented to ensure optimal performance and accurate filtering:
*   **`DateTable` (1) → `Flipkart_orders` (*):** Connected via `Date` and `Order Date`.
*   **`Flipkart_orders` (1) → `Flipkart_details` (*):** Connected via `Order ID`.
*   **Cross-filter direction:** Single (to maintain clean filter flow).

## 🧮 Key DAX Measures Created
```dax
Total Sales = SUM(Flipkart_details[Amount])

Total Profit = SUM(Flipkart_details[Profit])

Total Quantity = SUM(Flipkart_details[Quantity])

Total Orders = DISTINCTCOUNT(Flipkart_details[Order ID])

Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)

Avg Order Value = DIVIDE([Total Sales], [Total Orders], 0)
```

## 📊 Dashboard Features & Visuals
The dashboard is designed with a dark theme to match the Flipkart brand identity and includes:
*   **KPI Cards:** Total Sales, Total Profit, Total Orders, and Profit Margin.
*   **Donut Charts:** Distribution of Orders by PaymentMode and Categories by Quantity.
*   **Bar Charts:** Monthly Distribution of Profit and Top 5 Profitable Sub-Categories.
*   **Area Chart:** Monthly Distribution of Amount (Sales).
*   **Map Visual:** Geographic Distribution of Sales across Indian States.
*   **Pie Chart:** Orders by Day of the Week.
*   **Slicers:** Interactive Q1, Q2, Q3, and Q4 tile buttons for time-based filtering.

## 💡 Key Business Insights
*   **Payment Preferences:** Cash on Delivery (COD) accounts for the highest number of orders, followed by UPI and Credit Cards.
*   **Category Performance:** Clothing generates the highest volume of quantity sold, while Electronics and Furniture drive higher revenue per transaction.
*   **Profitability:** Printers, Bookcases, and Sarees are among the most profitable sub-categories. 
*   **Seasonality:** Sales tend to spike in the later months of the year (October to December), indicating a festive or end-of-year surge.
*   **Geography:** Sales are heavily concentrated in major states like Maharashtra, Uttar Pradesh, and Madhya Pradesh.

## 🚀 How to Use This Repository
1. Download the `Flipkart_Sales_Dashboard.pbix` file from this repository.
2. Open it using **Power BI Desktop** (free download from Microsoft).
3. If prompted, point the data source to the `Flipkart_details.csv` and `Flipkart_orders.csv` files located in the `/data` folder.
4. Explore the interactive slicers and visuals!

## 👨‍💻 Author
**[Mukesh Raj]**
*   LinkedIn: www.linkedin.com/in/mukesh-raj20


