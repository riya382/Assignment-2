# ShopEase - SQL Data Analysis Project

> CEI Internship | SQL Task 2 | Week 2

## About the Project

ShopEase is a fictional e-commerce platform. This project involves designing a relational database, inserting sample data, and running SQL queries to extract business insights using filtering, aggregation, joins, and transactions.

---

## Database Schema

The database contains 4 tables:

| Table | Description |
|-------|-------------|
| `customers` | Customer details — name, city, state, premium status |
| `products` | Product catalog — category, brand, price, stock |
| `orders` | Order records — date, status, total amount |
| `order_items` | Line items per order — quantity, price, discount |

### Relationships

```
customers
    └── orders (customer_id)
            └── order_items (order_id)
                    └── products (product_id)
```

---

## Project Structure

```
Assignment2/
├── data/
│   ├── schema.sql        # CREATE TABLE statements
│   ├── data.sql          # INSERT + all analysis queries
│   └── shopease.db       # SQLite database file
├── notebook/
│   ├── analysis.ipynb    # Jupyter Notebook with query results
│   └── superstore.csv    # Kaggle Superstore dataset
└── README.md
```

---

## Queries Covered

### Filtering (WHERE)
- Filter orders by status, date range
- Filter products by category and price
- Filter customers by state and join date

### Aggregations (GROUP BY)
- Total revenue from delivered orders
- Average price per product category
- Order count and revenue by status
- Max and min price per category

### Joins
- Customer names with their orders (INNER JOIN)
- All customers including those with no orders (LEFT JOIN)
- Order items with full product details (multi-table JOIN)

### Advanced
- CASE statements for price tier classification
- Transactions with COMMIT and ROLLBACK
- HAVING clause for filtered aggregations

---

## Tools Used

- MySQL Workbench
- DB Browser for SQLite
- Jupyter Notebook (Python + pandas)
- Kaggle Superstore Dataset

---

## Key Insights

- **Total delivered revenue**: Calculated using `SUM` with `WHERE status = 'Delivered'`
- **Electronics** is the highest priced category on average
- **Premium customers** (is_premium = TRUE) placed the most high-value orders
- Transactions ensure stock and order data stay consistent

---

## How to Run

1. Open MySQL Workbench
2. Run `data/schema.sql` to create the database and tables
3. Run `data/data.sql` to insert data and execute analysis queries
4. Open `notebook/analysis.ipynb` to view results with pandas

---

*Project by: [Riya Gupta] 
