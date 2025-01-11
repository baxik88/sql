# Type 1 SCD: Retain Address History

In a Type 1 Slowly Changing Dimension (SCD), each address change is recorded as a **new row**, preserving the entire history of a customer’s addresses.

## Table Structure

- **CustomerAddresses_Type1**
  - `address_id` (PK, auto-increment) 
  - `customer_id` (FK to `Customer`)
  - `address_line1`, `address_line2`, `city`, `state`, `zip_code`
  - `effective_start_date`
  - `effective_end_date` (NULL if currently active)

A single customer can have **multiple address rows** over time. Each row covers a distinct date range.

---

## Test Queries & Explanations

### 1. View Full Address History
```sql
SELECT 
  c.customer_id,
  c.first_name || ' ' || c.last_name AS customer_name,
  a.address_line1,
  a.effective_start_date,
  a.effective_end_date
FROM CustomerAddresses_Type1 a
JOIN Customer c ON a.customer_id = c.customer_id
ORDER BY c.customer_id, a.effective_start_date;
