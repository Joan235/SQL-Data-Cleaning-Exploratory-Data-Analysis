# SQL Data Cleaning & Exploratory Data Analysis

## Overview
This project uses SQL to clean and analyze a real-world dataset of company layoffs (2020–2023). The analysis focuses on preparing messy raw data for reliable analysis, then exploring patterns in layoffs across companies, industries, countries, funding stages, and time periods. After cleaning, the dataset contains 1,995 records covering 1,633 companies, 51 countries, and 30 industries, spanning March 2020 to March 2023.

## Objectives
- Clean and prepare the raw dataset for analysis.
- Identify and remove duplicate records.
- Standardize inconsistent values.
- Handle missing and blank values.
- Convert and standardize date values.
- Explore patterns and trends in company layoffs.
- Use SQL to answer analytical questions and generate insights.

## Data Cleaning
The data cleaning process included:
- Creating staging tables to preserve the original raw data.
- Identifying and removing duplicate records using `ROW_NUMBER()`.
- Standardizing company, industry, and country values (e.g. trimming whitespace, collapsing inconsistent industry labels like `Crypto`, `CryptoCurrency` into a single `Crypto` category, and removing a trailing period from `United States.`).
- Converting the `date` column from text to a proper `DATE` type.
- Identifying and handling missing values, including backfilling missing `industry` values where another record for the same company had it populated.
- Removing records where both `total_laid_off` and `percentage_laid_off` were missing, since those rows carried no usable layoff figure.

## Questions Explored
- Which companies recorded the highest total layoffs?
- Which industries recorded the highest total layoffs?
- Which countries recorded the highest total layoffs?
- How did layoffs change across different years?
- How did layoffs vary month by month?
- What is the cumulative number of layoffs over time?
- Which company stages recorded the highest total layoffs?
- Which companies ranked among the top companies for layoffs each year?
- Among companies with 100% layoffs, which had raised the most funding?

## Key Findings
- Amazon, Google, and Meta recorded the highest total layoffs of any company in the dataset, at 18,150, 12,000, and 11,000 employees respectively.
- The Consumer, Retail, and Other industries were hit hardest overall, together accounting for over 125,000 layoffs.
- The United States accounted for roughly two-thirds of all layoffs in the dataset (256,559 of 383,659), followed by India and the Netherlands.
- Layoffs were not evenly spread over time: after a 2020 pandemic-driven spike and a quieter 2021, layoffs surged again from late 2022 into early 2023, with January 2023 alone accounting for over 84,000 layoffs — more than any other single month.
- Post-IPO companies (large, publicly traded firms) recorded far more layoffs than any other funding stage, at over 204,000 — more than the next four stages combined.
- A small group of well-funded companies shut down entirely (100% of staff laid off), including Britishvolt, which had raised $2.4B, and Quibi, which had raised $1.8B — a reminder that funding raised doesn't guarantee survival.

## SQL Skills Demonstrated
- Data cleaning and transformation
- Duplicate detection using `ROW_NUMBER()`
- Handling missing values
- `JOIN` operations
- Common Table Expressions (CTEs)
- Window functions
- `DENSE_RANK()`
- Aggregations using `SUM()`, `AVG()`, `MIN()`, and `MAX()`
- Date and string functions
- Filtering, grouping, and sorting

## Tools
MySQL | SQL | GitHub

## Project Files
- `01_data_cleaning.sql` – data cleaning and preparation
- `02_exploratory_data_analysis.sql` – exploratory analysis and queries
- `layoffs.csv` – raw dataset used in this project

## Key Takeaway
This project demonstrates an end-to-end SQL workflow: taking a raw, messy dataset, improving its data quality through systematic cleaning, and using SQL to explore trends and turn query results into concrete, data-backed findings.
