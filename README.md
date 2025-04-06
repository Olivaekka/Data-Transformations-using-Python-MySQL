# Data-Transformations-using-Python-MySQL

# Video Game Sales Analysis: Pre-2005 vs Post-2005

## Description
This project performs a data analysis on global video game sales using a dataset from 2016. The focus is on comparing average global sales **before and after the year 2005**. The dataset is processed in Python and queried using MySQL to answer the following:

- Was the average of global sales higher before or after 2005?
- Label game records as 'Pre-2005' or 'Post-2005' using SQL logic in Python.
- Visualize the comparison using Matplotlib bar charts.

## Getting Started

### Prerequisites
To run this project, you will need the following:

- **Python 3.x**
- **Jupyter Notebook** (optional but recommended)
- **MySQL Server**
- **MySQL Workbench**
- **MySQL Connector for Python**
- **SQLAlchemy**
- **Pandas, NumPy, Matplotlib**

Install required Python libraries:

```bash
pip install pandas numpy matplotlib sqlalchemy pymysql
```

### Installing
Follow these steps to set up and run the project:

1. **Install MySQL Workbench and Server**  
   Download from [MySQL Website](https://dev.mysql.com/downloads/installer/).

2. **Create Database and Table**
   In MySQL Workbench, create a database and copy the original table to avoid modifying it:

```sql
CREATE DATABASE 1202_db;
USE 1202_db;
CREATE TABLE vgsalesproject3 LIKE vgsales;
INSERT INTO vgsalesproject3 SELECT * FROM vgsales;
```

3. **Edit Python Connection**
   In the script, update your credentials:

```python
engine = create_engine('mysql+pymysql://root:yourpassword@localhost/1202_db')
```

## Running the Code
- Open the Python script (`video_game_sales_analysis.py`) or run it in Jupyter Notebook.
- The script:
  - Connects to MySQL
  - Loads and cleans data using Pandas
  - Labels records using `np.where`
  - Calculates average global sales pre/post 2005
  - Updates the database
  - Visualizes the comparison using Matplotlib

## Running the Tests

### Breakdown of Tests
- **MySQL Connection Test** – Ensures connection between Python and the MySQL server.
- **Data Extraction** – Tests if the dataset is successfully loaded from MySQL into a DataFrame.
- **Year Conversion & Cleaning** – Ensures correct handling of invalid or missing year values.
- **Period Labeling** – Verifies correct labeling of rows as 'Pre-2005' or 'Post-2005'.
- **Sales Aggregation Test** – Validates average sales values using `.mean()` method.
- **Data Write-Back** – Confirms the updated DataFrame is pushed back into MySQL correctly.
- **Visualization** – Ensures the bar chart comparing pre/post 2005 sales displays as expected.

## Deployment
You can deploy this project locally, or optionally on a cloud server:

- **Local Deployment**: Run with Jupyter Notebook or standard Python script execution.
- **Cloud Deployment**: You can use platforms like AWS or Google Cloud with hosted MySQL and Python environments.
- **Visualization Hosting**: Use Flask or Streamlit to create a simple web app if desired.

## Author
#### Oliva Ekka | [LinkedIn Profile](https://www.linkedin.com/in/olivaekka/)

## Contributors

| Name               | LinkedIn        |
|--------------------|-----------------|
| Sakeena Raza       | [LinkedIn Profile](https://www.linkedin.com/in/sakeena-raza/) |
| Monika Dandriyal   | [LinkedIn Profile](https://www.linkedin.com/in/monika-dandriyal/) |
| Amad Arshad        | [LinkedIn Profile](https://www.linkedin.com/in/amad-arshad-088a38350/) |

## License
This project is not licensed. It was created as part of an academic submission for **DATA-1202 – Data Analysis and Analytics Tools**.

## Acknowledgements
- **Professor Omar Al-Trad** – For guidance throughout the project.
- **Pandas** – For data manipulation and preprocessing.
- **MySQL & SQLAlchemy** – For database integration.
- **Matplotlib** – For insightful visualizations.
- **np.where** – For effective data categorization.
