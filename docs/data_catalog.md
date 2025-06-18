# Data Dictionary for Gold Layer 
### Overview
The gold layer is the business-level data represetation, structured to support analytical and reporting use cases. It consists of __dimension tables__
and __fact tables__ for specific business metrics.

---

#### 1. gold.dim_customers
- __Purpose:__ stores customer details enriched with demographic and geographic data.
- __Columns:__

| Column Name   | Data Type | Description |
|---------------|-----------|-------------|
| customer_key | INT | Surrogate key uniquely identifying each customer record. |
| customer_id | INT | Unique numerical identifier assigned to each customer. |
| customer_number | INTVARCHAR | Alphanumeric identifier representing the customer, used for tracking and referencing. |
| first_name | VARCHAR | Customer's first name. |
| last_name | VARCHAR | Customer's last name. |
| country | VARCHAR | Customer's country of residence. |
| marital_status | VARCHAR | Customer's marital status. |
| gender | VARCHAR | Customer's gender. |
| birth_date | DATE | Customer's birthday name. |
| create_date | DATE | Creation date of customer's account. |

---

#### 2. gold.dim_products
- __Purpose:__ stores product details
- __Columns:__

| Column Name   | Data Type | Description |
|---------------|-----------|-------------|
| product_key | INT | Surrogate key uniquely identifying each product. |
| product_id | INT | Unique numerical identifier assigned to each product. |
| product_number | INTVARCHAR | Alphanumeric identifier representing the product, used for tracking and referencing. |
| category_id | VARCHAR | Identifier corresponding to the category of the product. |
| category | VARCHAR | Category that the product belongs to. |
| subcategory | VARCHAR | Subcategory that the product belongs to. |
| maintenance | VARCHAR | Status of whether the product has been maintained. |
| cost | INT | Cost of the product. |
| product_line | VARCHAR | Specific line the product is sold to. |
| start_date | DATE | Date of first selling the product. |

---

#### 3. gold.fact_sales
- __Purpose:__ stores sales details
- __Columns:__

| Column Name   | Data Type | Description |
|---------------|-----------|-------------|
| order_number | INTVARCHAR | Surrogate key uniquely identifying each sale. |
| product_key | INT | Unique numerical identifier referencing each product. |
| customer_key | INTVARCHAR | Alphanumeric identifier referencing the customer. |
| order_date | DATE | Date of sales order. |
| shipping_date | DATE | Date of product sent out for shipping. |
| due_date | VARCHAR | Date of expected product arrival. |
| sales_amount | INT | Total sales of product. |
| quantity | INT | Number of products sold. |
| price | INT | Price of each individual product sold. |
