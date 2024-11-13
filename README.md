# S&P 500 Log Returns Analysis Project

This project involves analyzing the log returns of the S&P 500 index and relevant economic indicators from the UK and the US, aiming to provide insights for macroeconomic forecasting and financial modeling. The code makes extensive use of data manipulation, visualization, and statistical analysis tools to derive meaningful conclusions about market dynamics. This repository showcases skills in data preprocessing, handling missing values, and applying econometric models, all of which are relevant for finance and machine learning applications in economics.

## Project Goals
- **Analyze and process financial and economic data:** Extract meaningful insights from raw financial data, focusing on the impact of macroeconomic indicators on S&P 500 returns.
- **Data Visualization and Statistical Modeling:** Use machine learning and econometrics tools to examine and visualize correlations and trends.
- **Time-Series Analysis:** Clean and resample data, manage missing values, and apply time series methods to interpret the data accurately.

## Key Tools and Libraries
The project leverages the following libraries and tools for data analysis, machine learning, and visualization:
- **`yfinance`**: For obtaining historical data of financial assets.
- **`pandas` and `numpy`**: For data manipulation, cleaning, and handling missing values.
- **`matplotlib`**: For visualizing trends and key indicators within the data.
- **`missingno`**: To identify and visualize missing values within the dataset.
- **`statsmodels`**: For applying statistical models and econometric analysis.

## Data Processing Steps
1. **Data Loading and Initial Inspection**: Load historical data and perform an initial check for missing values.
2. **Handling Missing Values**: Use a mix of `missingno` for visualization and `pandas` for interpolation and forward-filling to handle gaps in data.
3. **Date Manipulation and Resampling**: Adjust date indices to monthly frequency for macroeconomic indicators and ensure alignment of data across multiple sources.
4. **Data Shifting for Forecasting**: Shift certain columns to align current values with their subsequent impact, assisting in time-lagged analysis.
5. **Modeling and Statistical Analysis**: Use `statsmodels` to apply statistical models to the processed data.

## Dataset
The dataset used in this analysis includes economic indicators such as:
- **USD and UK 2-Year Bond Yields**
- **UK and US Year-over-Year Consumer Price Index (CPI)**
- **UK and US Industrial Indices**

This data provides a basis for understanding macroeconomic trends and examining their influence on market returns.

## Usage
To replicate the analysis, ensure the required libraries are installed, and run each cell in sequence to load and process the data.

```bash
pip install yfinance pandas matplotlib missingno statsmodels

##Future Work
Potential extensions include applying machine learning models for forecasting or exploring additional economic indicators. 

