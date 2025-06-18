# 📦 Consumer Goods Management - SQL Project

This project showcases how SQL can be used to answer business questions, generate insights, and support decision-making in the **Consumer Goods industry**. It involves real-world scenario-based requests, ad-hoc query writing, and analysis using a sample hardware sales database.

---

## 🧰 Tools & Technologies

- **SQL** – Core query language for data analysis
- **MySQL / PostgreSQL** – Compatible with most RDBMS
- **DB Browser / DBeaver** – For executing and testing queries

---

## 🎯 Project Objectives

- Practice solving real-world business queries using SQL
- Analyze supply chain, sales, and operations data
- Improve data-driven decision-making skills in a consumer goods context

---

## 📁 Repository Structure

📁 Request Answers/          # Folder containing answers to case-based business questions
📁 SQL Answers/              # Folder with structured SQL solutions
📄 Hints Project-Management In Consumer Goods.pdf  # Problem statement & hint guide
📄 Metadata.txt             # Column descriptions and table relationships
📄 ad-hoc-requests.pdf      # List of business questions to be solved
📄 atliq_hardware_db.sql    # Sample SQL database to import locally
📄 demo_sql_queries.txt     # Sample SQL code snippets for reference


---

## 📌 How to Use

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Utkrisht2026/Consumer-Goods-Management-SQL.git

# AtliQ Hardware Data Analysis Project

## 🛠️ Setup Instructions

1. **Import the database**:
   - Use a database tool like:
     - MySQL Workbench
     - DBeaver
     - DB Browser
   - Execute `atliq_hardware_db.sql` to set up the database

2. **Understand the schema**:
   - Refer to `Metadata.txt` for table relationships and column descriptions

## 📊 Analysis Workflow

1. **Review business cases**:
   - See `ad-hoc-requests.pdf` for practical SQL challenges
   - Use `Hints Project-Management In Consumer Goods.pdf` if needed

2. **Write and test your queries**:
   - Save your solutions in the `SQL Answers/` folder
   - Compare or refer to `demo_sql_queries.txt` for guidance

## 🧠 Example Business Questions

```sql
-- 1. Monthly sales trend by product category
SELECT 
    category,
    MONTH(order_date) AS month,
    SUM(sales_amount) AS total_sales
FROM sales
GROUP BY category, MONTH(order_date)
ORDER BY category, month;

-- 2. Top 5 revenue-contributing customers
SELECT 
    customer_name,
    SUM(sales_amount) AS total_revenue
FROM sales
GROUP BY customer_name
ORDER BY total_revenue DESC
LIMIT 5;

-- 3. Product availability impact on fulfillment
SELECT 
    product_id,
    AVG(fulfillment_rate) AS avg_fulfillment_rate,
    AVG(stock_availability) AS avg_availability
FROM inventory
GROUP BY product_id;

-- 4. Year-over-year sales growth
SELECT 
    YEAR(order_date) AS year,
    SUM(sales_amount) AS annual_sales,
    (SUM(sales_amount) - LAG(SUM(sales_amount)) OVER (ORDER BY YEAR(order_date))) / 
    LAG(SUM(sales_amount)) OVER (ORDER BY YEAR(order_date_date)) * 100 AS yoy_growth
FROM sales
GROUP BY YEAR(order_date);
```

## 📂 Project Structure
```
📁 Request Answers/          # Case-based business answers
📁 SQL Answers/              # Structured SQL solutions
📄 Hints Project-Management In Consumer Goods.pdf
📄 Metadata.txt             # Schema documentation
📄 ad-hoc-requests.pdf      # Business questions
📄 atliq_hardware_db.sql    # Database dump
📄 demo_sql_queries.txt     # Example queries
```

## 👨‍💻 Author

**Utkrisht Jalan**  
Aspiring Data Analyst skilled in SQL, Python, Power BI, and Excel.  
[GitHub Profile](https://github.com/Utkrisht2026)
