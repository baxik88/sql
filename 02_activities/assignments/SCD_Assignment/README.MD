# SCD Assignment

This repository contains two cases for handling Slowly Changing Dimensions (SCD): **Type 1 SCD (Retain Address)** and **Type 2 SCD (Overwrite Address)**. Each case includes a database file with test data, a README with explanations, and a diagram illustrating the schema.

---

## **Folder Structure**

### **1. SCD_type_1_retain_address**
- **Purpose**: Demonstrates Type 1 SCD logic, where the customer's address history is retained as separate records.
- **Contents**:
  - `README_type_1_retain_address.md`: Documentation explaining the logic of Type 1 SCD and providing test queries.
  - `type_1_retain_address_with_data.db`: SQLite database file with sample data for Type 1 SCD.
  - `type_1_retain_address.png`: Diagram of the schema used for Type 1 SCD.

### **2. SCD_type_2_overwrite_address**
- **Purpose**: Demonstrates Type 2 SCD logic, where only the current address is kept, and previous data is overwritten.
- **Contents**:
  - `README_type_2_overwrite_address.md`: Documentation explaining the logic of Type 2 SCD and providing test queries.
  - `type_2_overwrite_address_with_data.db`: SQLite database file with sample data for Type 2 SCD.
  - `type_2_overwrite_address.png`: Diagram of the schema used for Type 2 SCD.

---

## **How to Use**

1. **Database Files**:
   - Each folder contains a `.db` file with an SQLite database.
   - You can open these databases using any SQLite client (e.g., DB Browser for SQLite, SQLiteStudio, or `sqlite3`).

2. **Documentation**:
   - Each folder contains a `README.md` file with:
     - An explanation of the SCD type.
     - The table structures used in the schema.
     - Test queries to verify the database behavior.

3. **Diagrams**:
   - Each folder includes a `.png` file with a visual representation of the database schema for the respective SCD case.

---

## **Summary**

This project showcases two approaches to handling Slowly Changing Dimensions in a database:

- **Type 1 SCD**: Retains historical records of addresses by adding a new row for each change.
- **Type 2 SCD**: Overwrites the address, keeping only the current address for each customer.

Each case is self-contained within its respective folder, providing everything you need to understand and test the implementation.
