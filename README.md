# Global Transport & Delivery Analytics System (MySQL)

A comprehensive relational database project built to model global transport carriers, shipping routes, operational shipments, and freight costs, accompanied by advanced business intelligence analytics queries.

## 📊 Database Schema Architecture

The database consists of 4 core normalized tables linked via Foreign Keys to ensure transactional integrity:

- **carriers:** Stores logistics partner details, country of origin, service types (Air, Ocean, Ground), and performance ratings.
- **routes:** Manages origin and destination city pairs along with estimated scheduling dates.
- **shipments:** The core tracking table capturing dispatch dates, estimated vs. actual delivery dates, and real-time statuses (`In Transit`, `Delivered`, `Delayed`).
- **shipment_cost:** Records shipment weight, fuel surcharges, and total freight costs linked directly to individual tracking numbers.

---

## ⚙️ SQL Implementation & Features

- **Referential Integrity:** Utilizes Foreign Key constraints with `ON DELETE SET NULL` rules to maintain data safety and historical consistency when parent records are updated or deleted.
- **Conditional Aggregation:** Leverages `SUM(CASE WHEN ...)` logic to calculate specific status counts (delivered vs. delayed shipments) in a single pass.
- **Business Intelligence Analytics:** Combines multi-table `LEFT JOIN` operations and `GROUP BY` clauses to generate executive summaries of carrier performance, total shipping volumes, and total revenue generation.

---

## 📁 Repository Structure

```text
├── global_transport_analytics.sql   # Complete database schema, seed data, and analytical queries
