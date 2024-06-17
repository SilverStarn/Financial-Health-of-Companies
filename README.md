# Financial-Health-of-Companies

## Project Overview

This project analyzes the financial health of companies by examining their profit metrics. The analysis involves data cleaning, transformation, and visualization to provide insights into the distribution of profits among various companies. The primary analysis is contained within the Jupyter Notebook `1000_Companies_Financial_Analysis.ipynb`.

## Files in the Repository

- `1000_Companies_Financial_Analysis.ipynb`: Jupyter Notebook containing the analysis.
- `1000_Companies_revised.csv`: Dataset containing financial information about various companies.

## Notebook: 1000_Companies_Financial_Analysis.ipynb

### Objective

The main objective of this notebook is to analyze the profit data of companies, focusing on understanding the distribution and categorization of profit metrics. The analysis is structured to:
- Clean and preprocess the data
- Transform the data for better analysis
- Visualize the results to draw meaningful insights

### Data

The dataset used in this analysis is `1000_Companies_revised.csv`, which contains financial information about various companies. The dataset includes columns such as:
- `R&D Spend`
- `Administration`
- `Marketing Spend`
- `State`
- `Profit`

### Steps in the Notebook

1. **Setup and Data Loading**
   - Import necessary libraries (`pandas`, `matplotlib`)
   - Load the dataset `1000_Companies_revised.csv`

2. **Initial Data Inspection**
   - Display the first few rows of the dataset to understand its structure

3. **Data Cleaning and Preparation**
   - Check for and handle missing values
   - Convert the `Profit` column to numeric and remove rows with non-numeric profit values
   - Save the cleaned data

4. **Feature Engineering**
   - Bin the `Profit` data into three categories: Low, Medium, and High
   - Save the binned data

5. **Data Visualization**
   - Create a bar plot to visualize the distribution of companies by profit bins

### Key Functions and Code Snippets

- **Data Loading and Cleaning:**
  ```python
  import pandas as pd

  # Load the data
  companies = pd.read_csv('1000_Companies_revised.csv')

  # Display the first few rows of the dataset
  print(companies.head())

  # Check for missing values
  print(companies.isnull().sum())

  # Drop rows with missing data
  companies.dropna(inplace=True)

  # Convert 'Profit' column to numeric
  companies['Profit'] = pd.to_numeric(companies['Profit'], errors='coerce')

  # Drop rows with missing 'Profit' values
  companies.dropna(subset=['Profit'], inplace=True)
