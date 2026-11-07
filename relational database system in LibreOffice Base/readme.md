# Sales & Inventory Management System (`sales.odb`)

A relational database management system built using **LibreOffice Base** designed to streamline order processing, customer tracking, and inventory control for small-to-medium retail operations.

---

## Project Overview

The **Sales & Inventory Management System** models real-world business transactions through normalized relational tables. Built to demonstrate strong core database design principles, it eliminates data redundancy, enforces referential integrity, and provides actionable insights via SQL querying and custom reports.

* **Database Engine:** LibreOffice Base (HSQLDB Embedded Engine)
* **Architecture Standard:** 3rd Normal Form (3NF)
* **Target Application:** Inventory & Sales Operations Tracking

---

## Database Architecture & Schema

The system consists of four primary relational tables connected via **One-to-Many ($1:N$)**  relationships.

```
+-------------------+         +-------------------+         +-------------------+   
|   TblCustomers    |         |      TblSales     |         |    TblProducts    |
+-------------------+         +-------------------+         +-------------------+
| CustomerID  (PK)  |<---|    | SalesID     (PK)  |   ----->| ProductID     (PK)|
| CustomerName      |    |----| CustomerID        |    |    | Product           |
| Address           |         | ProductID         |-----    | Qty               |
| City              |         | Qty               |         | Price             |
+-------------------+         | DatePurchased     |         +-------------------+
                              +-------------------+          
```

### Table Definitions

1. **`TblCustomers`**: Manages unique customer contact profiles.
2. **`TblProducts`**: Tracks product inventory levels, pricing, and category classifications.
3. **`TblSales`**: Serves as a junction table resolving the $M:N$ relationship between orders and products while keeping line-item sub-totals.

## Table And Queries Image
![Alt, table and query](relational database system in LibreOffice Base/tables and query.png)

