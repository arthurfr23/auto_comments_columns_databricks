# auto_comments_columns_databricks

Automatic Generation of Column Descriptions in Databricks
This script automates the generation of column descriptions for tables in a Databricks environment. It uses Databricks' Genie combined with AI-driven models to generate business descriptions for each column based on their names and data types. The goal is to facilitate accurate metadata generation and improve queries and correlations between tables for data analysis.

How It Works:
Catalog and Schema Reading:

The script starts by dynamically reading the catalog and schema in Databricks and collects all the tables from the specified schema.
Generate Column Descriptions:

For each table, the script creates a function that generates column descriptions using an AI model. The model is instructed to provide accurate, metadata-rich descriptions based on the column name, data type, and the first 50 rows of data from each column for better accuracy.
Temporary View Creation:

A temporary view is created to store the generated column descriptions. These descriptions are stored alongside the data type and the current date.
Alter Column Comments:

The generated descriptions are applied as comments to the respective columns in the tables. The comments are added directly to the Unity Catalog using the ALTER TABLE command in Databricks.
Requirements:
Databricks Environment with the Unity Catalog enabled.
Databricks SQL and PySpark environment to execute the SQL queries and Python code.
