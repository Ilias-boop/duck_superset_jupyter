# Open-source/lightweight BI Stack: Jupyter + DuckDB + Superset

This project provides an open-source and lightweight BI stack to explore, analyze, and visualize data (an example of Moroccan crop production data is used).

- Jupyter Notebook for data preparation and analysis

- DuckDB for fast SQL queries and data storage

- Apache Superset for data visualization and exploration

This project is ideal for BI Engineers or Data Analysts looking for an alternative to Power BI/Tableau without heavy installations.

# Installation & Setup

1. Install Dependencies

Ensure you have Python 3.8+ and install the required packages:
```
pip install duckdb pandas jupyter apache-superset
```
2. Start Jupyter Notebook
```
jupyter notebook
```
3. Create the DuckDB Database

Inside a Jupyter Notebook:
```
import duckdb
import pandas as pd

df = pd.read_excel("20230714-production-vegetale-2010-2022.xlsx")
con = duckdb.connect("production_vegetale.db")
con.execute("CREATE TABLE production AS SELECT * FROM df")
```
4. Start Apache Superset
```
superset db upgrade
superset fab create-admin  # Create an admin account
superset run -p 8088 --with-threads --reload --debugger
```
Then, go to http://localhost:8088 and log in.

# Do the Data Analysis that you want

# Visualization with Apache Superset

- Add DuckDB as a Data Source in Superset

Go to Sources > Databases

Add a new connection with the following URI:
```
duckdb:///path/to/production_vegetale.db
```
Validate and test the connection

- Create a Dashboard

Go to Sources > Tables and add the `production` table

In Explore, create interactive charts (bar, line, etc.)

Save and organize them into a Dashboard

# Key Benefits of This BI Stack

+ No heavy installations (no PostgreSQL, no BI server needed)
+ Fast and efficient SQL queries with DuckDB
+ Advanced and interactive visualizations with Superset
+ Exploratory analysis and Machine Learning possible with Jupyter
+ 100% Open-source and free
