# Online Food Ordering System – Database (MySQL)

This repository contains the relational database design and SQL script for an **Online Food Ordering System**.  
It focuses on modeling the core entities of the platform (customers, restaurants, menu items, orders, payments, delivery, ratings) and provides seeded sample data for analysis and reporting. :contentReference[oaicite:1]{index=1}

---

## 📚 Project Overview

The goal of this database is to:

- Store customer, restaurant and menu information in a structured, normalized form  
- Track orders, payments and delivery details end-to-end  
- Capture customer ratings to evaluate restaurant performance  
- Enable analytical queries for:
  - Customer behavior & engagement
  - Restaurant performance
  - Revenue & business metrics
  - Operational efficiency
  - Customer satisfaction & feedback

This schema is intended for use in an academic DBMS / SQL project and can be executed in **MySQL Workbench** or any MySQL-compatible environment.

---

## 🧱 Database Schema

**Database name**

- `food_ordering`

**Main tables**

1. `Admin`  
   - Stores admin user credentials who manage the platform.  
   - Key columns: `Admin_id`, `Admin_name`, `Admin_password`.

2. `customer`  
   - Stores customer profile details.  
   - Key columns: `customer_id`, `customer_firstname`, `customer_lastname`, `customer_phoneno`, `customer_email`, `customer_address`, `Admin_id (FK)`.

3. `restaurant`  
   - Stores restaurant accounts registered on the platform.  
   - Key columns: `restaurant_id`, `restaurant_name`, `restaurant_address`, `restaurant_phoneno`, `restaurant_password`, `Admin_id (FK)`.

4. `category`  
   - Represents menu categories / cuisines per restaurant (e.g., SOUTH-INDIAN, ITALIAN).  
   - Key columns: `category_id`, `category_name`, `restaurant_id (FK)`.

5. `Menu_items`  
   - Stores individual menu items offered by restaurants.  
   - Key columns: `item_code`, `item_name`, `Price`, `category_id (FK)`.

6. `Payment_details`  
   - Stores payment mode and timestamp for each payment.  
   - Key columns: `payment_id`, `payment_mode`, `payment_timestamp`.

7. `delivery_details`  
   - Stores delivery address and delivery status.  
   - Key columns: `delivery_id`, `delivery_address`, `delivery_status`.

8. `Order_details`  
   - Represents an order header (one row per order).  
   - Key columns: `Order_id`, `Order_time`, `Order_amount`, `Order_status`, `customer_id (FK)`, `delivery_id (FK)`, `payment_id (FK)`, `restaurant_id (FK)`.

9. `Orders`  
   - Represents line items for each order (which items and quantities were ordered).  
   - Key columns: `Order_id (FK)`, `item_code (FK)`, `quantity`.

10. `Rating`  
    - Stores customer ratings for restaurants.  
    - Key columns: `ratings`, `customer_id (FK)`, `restaurant_id (FK)`.

The script also inserts **sample records** into each table so you can immediately run SELECT and analytical queries.

---

## 🚀 Getting Started

### Prerequisites

- MySQL Server (8.x recommended)
- MySQL Workbench (or any other MySQL client)

### 1. Clone or download the repository

```bash
git clone <https://github.com/premwadekar28/Food-Ordering-SQL.git>
cd <https://github.com/premwadekar28/Food-Ordering-SQL>
