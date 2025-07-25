# MIS 311: Introduction to Business Analytics

## Assignment 1: Personal Portfolio Site

Name: Nguyen Do Xuan Ai

IRN: 2332300353

Dataset: Cost of Living

## 1. An Overview

This dataset offers a snapshot of economic well-being across a diverse range of countries, including Australia, Brazil, China, Germany, India, Japan, Mexico, Russia, South Africa, and the United States, for various years between 2000 and 2023. It is designed to explore the relationship between earnings and expenses in different parts of the world.

The dataset is structured around five key columns:

- Country (object): The name of the country where the data was recorded.

- Year (int): The year when the data was recorded.

- Average_Monthly_Income (float64): The average monthly income of individuals in USD.

- Cost_of_Living (float64): The average monthly cost of living in USD, including essentials like housing, food, and utilities.

- Region (object): The geographical region to which the country belongs.

Dataset Details:

Number of Rows: 201

Number of Columns: 5

The data appears to provide a historical and cross-sectional view of economic conditions in various countries, capturing income and cost of living metrics over different years. This can be used to analyze affordability, economic trends, and regional differences in living standards.

## 2. Data Cleaning

### 1. Missing Values

To identify missing values, I analyzed the dataset for any null or empty entries in each column.

### Findings:

Average_Monthly_Income: 2 missing values (rows 162 and 178).

Region: 2 missing values (rows 26 and 39).

Country, Year, Cost_of_Living: No missing values.

### Handling Missing Values:

Average_Monthly_Income:

For row 162 (Australia, 2012), I propose imputing the missing income using the average Average_Monthly_Income for Australia across other years in the dataset. Calculating the mean income for Australia

<img width="351" height="266" alt="image" src="https://github.com/user-attachments/assets/d513bbda-3122-44d9-abc7-96e886599e79" />

For row 178 (Mexico, 2006), impute using the mean Average_Monthly_Income for Mexico across other years

<img width="275" height="278" alt="image" src="https://github.com/user-attachments/assets/5e748f09-37cb-44e4-b632-39b6b6660cee" />

Reason: Imputing missing Average_Monthly_Income values with country-specific means preserves economic context and minimizes bias by leveraging historical data from the same country.

Region:

For row 26 (Mexico, 2003), assign "North America" as the region, consistent with other Mexico entries.

For row 39 (Mexico, 2000), assign "North America" as the region, consistent with other Mexico entries.

Reason: Imputing numerical values with country-specific means preserves trends and avoids introducing bias. For categorical data (Region), assigning the known region for the country ensures consistency.

### 2. Duplicates

To identify duplicates, I checked for rows with identical values across all columns (Country, Year, Region, Average_Monthly_Income, Cost_of_Living).

### Findings:

Rows 42 and 45 (Mexico, 2010, 6729.65, 943.71, North America) are identical.

Rows 30 and 37 (China, 2022, 7924.7, 5484.69, Asia) are identical.

### Handling Duplicates:

Remove one of the duplicate rows for each pair:

Keep row 42, remove row 45.

Keep row 30, remove row 37.

Result: Reduces dataset to 199 rows.

# 3. Insights:

## 3.1. Insights 1:

Australia has the highest average monthly income at $5,116, while its average cost of living is only $3,770, offering a strong surplus of $1,346. Russia’s average income is $4,675 compared to a cost of living of $4,361, showing a narrow margin of just $314. South Africa presents a similar situation, with a average income of $4,568 and cost of living at $4,442. Brazil has the lowest average income at $4,060, but its average cost of living is relatively low at $3,080, leaving a modest surplus of $980. Germany shows a balanced profile with a average income of $4,412 and cost of living of $3,895, giving a difference of $517.

<img width="1790" height="790" alt="image" src="https://github.com/user-attachments/assets/b655a780-9ffd-4fdb-9418-80c3d8aeb83f" />

## 3.2. Insights 2:

Africa has the highest average cost of living at $3,963, slightly exceeding Oceania at $3,913, which is unexpected given common assumptions about affordability in developing regions. Europe reports the lowest average cost of living at $3,554, even lower than South America ($3,585) and Asia ($3,645), indicating possible cost-efficiency in several European countries. North America sits in the mid-range at $3,750, reflecting moderate living costs compared to other high-income regions. The cost differences between regions are narrow — mostly ranging between $3,500 and $4,000.

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/81d0956a-bfb0-4939-b829-a73c6041b33b" />
