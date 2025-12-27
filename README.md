# Customer_Behavior_Analysis

📊 Data Analytics – Customer Behavior Analysis
🔍 Overview
This project focuses on analyzing customer behavior using an end-to-end data analytics workflow. It covers data loading, cleaning, exploratory analysis, SQL-based insights, and interactive visualization to support data-driven decision-making.





📁 Dataset

Customer transaction and demographic dataset
Includes: customer ID, age, gender, purchase amount, discounts, product ratings, subscriptions, and shipping details
Dataset type: Structured (CSV / SQL table)

🛠 Tools & Technologies

Python: Pandas, NumPy, Matplotlib, Seaborn
SQL: MySQL, SQL Server
Power BI: Dashboard & visualization
GitHub: Version control

🔄 Project Workflow

Load dataset using Python
Perform data cleaning and preprocessing
Conduct Exploratory Data Analysis (EDA)
Run analytical SQL queries
Build Power BI dashboards
Generate report and presentation


🧪 Python – Data Loading & Cleaning

import pandas as pd

# Load dataset
df = pd.read_csv("customer_data.csv")

# Basic inspection
df.head()
df.info()

# Handle missing values
df.dropna(inplace=True)

# Convert data types
df['purchase_amount'] = df['purchase_amount'].astype(float)


📊 Python – Exploratory Data Analysis (EDA)

import matplotlib.pyplot as plt
import seaborn as sns

# Purchase distribution
sns.histplot(df['purchase_amount'], bins=30)
plt.title("Purchase Amount Distribution")
plt.show()

# Revenue by gender
df.groupby('gender')['purchase_amount'].sum().plot(kind='bar')
plt.title("Revenue by Gender")
plt.show()



🗄 SQL – Sample Analytical Queries
Revenue by Gender

SELECT gender,
       SUM(purchase_amount) AS total_revenue
FROM customer
GROUP BY gender;

🗄 Customer Segmentation by Age Group

WITH age_data AS (
    SELECT
        CASE
            WHEN age BETWEEN 18 AND 25 THEN 'Young Adult'
            WHEN age BETWEEN 26 AND 40 THEN 'Adult'
            WHEN age BETWEEN 41 AND 60 THEN 'Middle-age'
            ELSE 'Senior'
        END AS age_group,
        purchase_amount
    FROM customer
)
SELECT age_group,
       SUM(purchase_amount) AS total_revenue
FROM age_data
GROUP BY age_group
ORDER BY total_revenue DESC;



📊 Power BI Dashboard

The Power BI dashboard includes:
Revenue trends and KPIs
Customer segmentation (age, gender, subscription)
Product performance and ratings
Discount and shipping impact
The dashboard is interactive and designed for business stakeholders.

📈 Key Insights

Identified high-value customer segments
Analyzed product performance and ratings
Observed spending behavior across age groups
Evaluated impact of discounts and subscriptions on revenue




