# Type 2 SCD: Overwrite the Address

In a Type 2 Slowly Changing Dimension (SCD), we keep **only the current address** for each customer.  
When a customer’s address changes, the data in `CustomerAddresses_Type2` is **overwritten**, so no previous address remains.

## Table Structure 

- **CustomerAddresses_Type2**
  - `customer_id` (PK, also FK to `Customer`)
  - `address_line1`, `address_line2`, `city`, `state`, `zip_code`
  - `last_updated` (date/time the row was last updated)

There is exactly **one address row per customer**. If they move, we simply update that row.

---

## Test Queries & Explanations

### 1. Verify One Address per Customer
```sql
SELECT 
  customer_id,
  COUNT(*) AS address_count
FROM CustomerAddresses_Type2
GROUP BY customer_id;
