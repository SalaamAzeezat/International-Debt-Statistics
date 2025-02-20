# 💰 Analysing International Debt Statistics
#### 📍 Tools Used: SQL
#### 📌 Dataset Source: World Bank via DataCamp

## 📌 Project Goal
As humans take on debts to manage necessities, countries take on debt to manage their economy. This allows the provision of infrastructure required for a country's citizens to lead comfortable lives. This project examines the international debt burden across various countries, focusing on economic reliance on external loans. The aim is to answer these questions:
- The number of distinct countries in the dataset.
- Which country holds the highest debt?
- Which country has the lowest repayment amounts?
## 📂 Dataset Information
- Data collected by the World Bank.
- Includes details on country-wise debt levels across different financial instruments.
## 🛠️ Techniques Used
- SQL Queries for Data Retrieval
- Aggregation & Ranking
- Comparative Analysis Across Countries
## 📊 SQL Queries Used:
**Query:**
##### Dataset Preview
````sql
SELECT * 
FROM international_debt;
````
<img width="917" alt="Screenshot 2025-02-20 at 15 16 32" src="https://github.com/user-attachments/assets/edb25d91-9ebc-412e-9a54-d11760c5d16f" />

##### Finding the Number of Unique Countries:
````sql
SELECT COUNT(DISTINCT country_name) AS total_distinct_countries
FROM international_debt;
````
<img width="915" alt="Screenshot 2025-02-20 at 15 16 54" src="https://github.com/user-attachments/assets/670932b9-2f66-4cb5-9582-b17faecee09c" />

##### Identifying the Country with the Highest Debt:
````sql
SELECT country_name, SUM(debt) AS total_debt
FROM international_debt
GROUP BY country_name
ORDER BY total_debt DESC
LIMIT 1;
````
<img width="913" alt="Screenshot 2025-02-20 at 15 17 05" src="https://github.com/user-attachments/assets/ca9886c3-aea0-4b91-b1a3-a824f281aae7" />

##### Identifying the Country with the Lowest Repayment Amounts:
````sql
SELECT country_name, indicator_name, MIN(debt) AS lowest_repayment  
FROM international_debt
WHERE indicator_code = 'DT.AMT.DLXF.CD'
GROUP BY country_name, indicator_name
ORDER BY lowest_repayment
LIMIT 1;
````
<img width="919" alt="Screenshot 2025-02-20 at 15 17 25" src="https://github.com/user-attachments/assets/d37a2440-5219-4bd2-ad20-66655e3869bf" />

## 📌 Key Insights Extracted
- Some developing countries have debt levels exceeding their GDP.
- Debt repayment structures vary significantly, impacting economic stability.
## Recommendations
- Governments should optimise debt management strategies to prevent economic collapse.
