Customer Analytics Data Warehouse
Experiment 1 – Design Star and Snowflake Schema
Project Overview
This project demonstrates how customer and account information can be organized in a data warehouse using Star Schema and Snowflake Schema designs. The use case is bank customer churn analysis.

The dataset attributes described in the experiment include credit score, geography, gender, age, account balance, tenure, number of products, credit-card ownership, active membership, estimated salary and churn status.
Objectives
- Understand data warehouse schemas.
- Design a Star Schema.
- Design a Snowflake Schema.
- Identify fact and dimension tables.
- Compare the two schema designs.
Database and Tools
- Database: PostgreSQL
- Language: SQL
- Concepts: Fact table, dimension tables, primary keys, foreign keys, Star Schema and Snowflake Schema
Schema Design
Star Schema
The central fact table is fact_customer_churn. It references:
- dim_customer
- dim_geography
- dim_gender
The dimension tables are directly connected to the fact table.
Snowflake Schema
The central fact table is fact_customer_churn. The customer dimension is normalized and contains foreign keys referencing:
- dim_geography
- dim_gender
This reduces repetition in descriptive data, while queries may require additional joins.
Main Fact Table
FACT_CUSTOMER_CHURN contains:
- churn_fact_id – primary key
- customer_key, geography_key, gender_key – foreign keys
- credit_score, age, tenure, balance
- num_of_products, has_cr_card, is_active_member
- estimated_salary, exited (1 = left, 0 = stayed)
Files
- Customer_Analytics_Data_Warehouse_Experiment_1.pdf – updated experiment PDF
- Customer_Analytics_Data_Warehouse_Experiment_1.docx – editable Word document
- customer_analytics_data_warehouse.sql – PostgreSQL table creation and sample query
- README.md – project documentation
How to Run the SQL
1. Install and open PostgreSQL (for example, through pgAdmin).
2. Create or select a database for this experiment.
3. Open the Query Tool.
4. Open customer_analytics_data_warehouse.sql.
5. Execute the complete script.
6. Expand the customer_analytics_star and customer_analytics_snowflake schemas to inspect the tables.
7. Run the sample analytical query at the end of the SQL script.
Expected Output
The script creates separate database schemas for the Star and Snowflake designs, creates their fact and dimension tables, inserts one sample customer into the Star Schema, and runs a sample churn summary grouped by geography and gender.
Important Source-Document Note
The supplied PDF's written fact-table and dimension-table definitions describe customer churn fields. However, the embedded diagrams on pages 2 and 4 visibly include campaign/contact/outcome/time fields and a marketing-oriented fact table. To avoid silently changing the experiment, the updated document retains the source diagrams, while the SQL implementation follows the written FACT_CUSTOMER_CHURN, DIM_CUSTOMER, DIM_GEOGRAPHY and DIM_GENDER definitions. Confirm with your instructor whether the diagrams should be replaced with diagrams matching the written churn schema before final submission.
Result
The Star Schema and Snowflake Schema for the Customer Analytics Data Warehouse are represented using a central customer churn fact table and related dimension tables
