# 📚 Composite and Foreign Keys: Basic_services and Economic_indicators Tables
This project demonstrates how to split a larger dataset into smaller tables and link them through composite keys and foreign keys using MySQL.

---
## 🧠 Learning Objectives
- Understand how to create composite primary keys.

- Understand how to create a foreign key that references another table’s primary key.

- Practice relational database design with MySQL Workbench and pymysql (for Python integration).

- Strengthen database normalization skills.

---
## 🛠️ Setup Requirements
- MySQL Server installed locally.

- MySQL Workbench.

- Access to the `united_nations` database.

- Python 3 (optional if connecting via pymysql).

- Not compatible with Google Colab (requires local server access).

---
## 🗄️ Tables Created
1. Basic_services Table
- Purpose: Stores data on basic services access for each country and year.

- Columns:

  - `Country_name` (VARCHAR) — referenced from `Countries` table.
  
  - `Time_period` (INT) — year of data.
  
  - `Pct_managed_drinking_water_services` (DECIMAL).
  
  - `Pct_managed_sanitation_services` (DECIMAL).

- Primary Key: (`Country_name`, `Time_period`)

- Foreign Key: `Country_name` references `Countries(Country_name)`

2. Economic_indicators Table
- Purpose: Stores economic indicator data for each country and year.

- Columns:

  - `Country_name` (VARCHAR) — referenced from `Countries` table.
  
  - `Time_period` (INT) — year of data.
  
  - `GDP_per_capita` (DECIMAL).
  
  - `Unemployment_rate` (DECIMAL).

- Primary Key: (`Country_name`, `Time_period`)

- Foreign Key: Country_name references `Countries(Country_name`)

## 📌 Notes
- Composite keys help uniquely identify records using two fields together.

- Foreign keys ensure referential integrity between related tables.

- Always ensure referenced tables exist before creating foreign key constraints.

---
📸 Example SQL Queries

```
CREATE TABLE Basic_services (
    Country_name VARCHAR(255),
    Time_period INT,
    Pct_managed_drinking_water_services DECIMAL(5,2),
    Pct_managed_sanitation_services DECIMAL(5,2),
    PRIMARY KEY (Country_name, Time_period),
    FOREIGN KEY (Country_name) REFERENCES Countries(Country_name)
);

CREATE TABLE Economic_indicators (
    Country_name VARCHAR(255),
    Time_period INT,
    GDP_per_capita DECIMAL(10,2),
    Unemployment_rate DECIMAL(5,2),
    PRIMARY KEY (Country_name, Time_period),
    FOREIGN KEY (Country_name) REFERENCES Countries(Country_name)
);
```
## 📖 How to Run
1. Open MySQL Workbench and connect to your local server.

2. Select your `united_nations` database.

3. Run the provided SQL queries.

4. (Optional) Use pymysql in Python to interact with the tables.

---
👩‍💻 Author
Developed as part of ExploreAI Academy coursework.




