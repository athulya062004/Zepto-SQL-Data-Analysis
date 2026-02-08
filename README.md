# Zepto-SQL-Data-Analysis
SQL-based data analysis project using PostgreSQL to extract business insights from grocery product data inspired by Zepto.
# Zepto SQL Data Analysis (PostgreSQL)

## 📌 Project Overview
This project focuses on analyzing grocery product data inspired by Zepto using PostgreSQL. 
The objective is to clean raw data, explore patterns, and extract meaningful business insights 
related to pricing, discounts, inventory, and category-wise performance.

---

## 📊 Dataset Description
The dataset contains product-level information such as:
- Product name and category
- MRP and discounted selling price
- Discount percentage
- Available quantity and stock status
- Product weight (in grams)

---

## 🛠 Tools & Technologies
- PostgreSQL
- SQL
- pgAdmin 4

---

## 🔍 Key Analysis Performed

### 1. Data Exploration
- Total number of products
- Identification of null values
- Distinct product categories
- In-stock vs out-of-stock analysis
- Duplicate product name detection

### 2. Data Cleaning
- Removed products with invalid pricing
- Converted prices from paise to rupees
- Ensured data consistency for analysis

### 3. Business Insights
- Top discounted products offering best value
- High MRP products that are out of stock
- Estimated revenue per product category
- Identification of premium products with low discounts
- Best value products based on price per gram
- Product segmentation based on weight (LOW, MEDIUM, BULK)
- Total inventory weight per category

---

## 📈 Sample SQL Insights

```sql
SELECT category,
SUM(discountedSellingPrice * availableQuantity) AS total_revenue
FROM zepto
GROUP BY category
ORDER BY total_revenue DESC;
