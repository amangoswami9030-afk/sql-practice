# 🗄️ SQL Practice

A collection of SQL queries I've written while practicing
and improving my database skills.

---

## 📌 Topics Covered

| Topic | Status |
|-------|--------|
| SELECT & Filtering | ✅ Done |
| Joins (INNER, LEFT, RIGHT) | ✅ Done |
| GROUP BY & Aggregations | ✅ Done |
| Subqueries | 🔄 In Progress |
| Window Functions | 🔄 In Progress |
| Stored Procedures | 📅 Upcoming |

---

## 🧠 Sample Query — Sales Analysis

```sql
SELECT 
    region,
    COUNT(order_id) AS total_orders,
    SUM(sales_amount) AS total_revenue,
    ROUND(AVG(sales_amount), 2) AS avg_order_value
FROM sales
WHERE order_date >= '2024-01-01'
GROUP BY region
ORDER BY total_revenue DESC;


Sample Query — Top 5 Customers

SELECT 
    customer_name,
    SUM(purchase_amount) AS total_spent
FROM customers
JOIN orders ON customers.id = orders.customer_id
GROUP BY customer_name
ORDER BY total_spent DESC
LIMIT 5;
