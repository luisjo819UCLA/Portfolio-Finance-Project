# USD-GBP Exchange Rate Forecasting Project

This project leverages historical economic data to develop a trading strategy for forecasting the USD to GBP exchange rate. Using a dataset of economic indicators from the US and UK, we apply statistical and financial modeling to estimate exchange rate fluctuations and design a trading strategy based on Taylor rule fundamentals.

## Project Overview

The main objectives are:
1. **Data Collection and Preprocessing**: Load and clean economic data for the US and UK.
2. **Modeling Exchange Rate Movements**: Using Taylor rule fundamentals, forecast exchange rate changes based on economic indicators.
3. **Optimization**: Identify hyperparameters that optimize cumulative returns, geometric mean, Sharpe ratio, and annualized returns.

## Data Sources

The dataset comprises several economic indicators:
- **Interest Rates**: 2-year treasury yields from both countries.
- **Inflation**: Year-over-year CPI data.
- **GDP Indicator**: Industrial index as a proxy for GDP.
- **Exchange Rate**: USD to GBP exchange rate, sourced via the `yfinance` library.

Data spans from 2003 to 2024 and includes daily values for interest rates, inflation, and GDP proxies, with monthly exchange rate values. 

## Project Structure

### 1. Data Preprocessing

- Load and clean data (`final_project_data.csv`).
- Handle missing values due to the monthly release frequency of certain indicators.
- Convert interest rates to daily log returns and exchange rates to monthly log returns for consistency.

### 2. Feature Engineering

- Create a moving average of the yield differential (`Y_diff`) as a key input for forecasting.
- Transform interest rates and inflation indicators into simple returns for regression modeling.
- Calculate the output gap using the linear trend model to derive potential GDP growth for each country.

### 3. Forecasting Strategy

#### Model
The model forecasts exchange rate fluctuations using:
- **Inflation Differential**: Difference between US and UK inflation.
- **Output Gap Differential**: Derived from the Industrial index.
- **Yield Differential**: Differential between the US and UK 2-year yields.

#### Forecasting Steps
- Use a rolling window approach to generate out-of-sample forecasts for exchange rate changes.
- Estimate the change in exchange rates using the differential indicators in a Taylor rule-inspired model.

### 4. Optimization of Hyperparameters

Optimize hyperparameters (`output_window` and `exchange_window`) to maximize the Sharpe ratio and annualized return. This project found:
- **Optimal Output Window**: 24 months for potential GDP estimation.
- **Optimal Exchange Forecast Window**: 108 months for exchange rate prediction.

### 5. Strategy Performance

The strategy performance is evaluated by:
- **Cumulative Returns**: Visualized as an equity line.
- **Annualized Returns**: Calculated based on cumulative returns over the sample period.
- **Sharpe Ratio**: Measures risk-adjusted returns for the model.

### Key Results

With the optimal window selection:
- **Maximum Sharpe Ratio**: ~0.992
- **Maximum Annualized Return**: ~5.23%

The strategy was robust, as demonstrated by similar returns across various output and forecast windows.

## Visualization

- **Heatmap of Geometric Return**: Visualizes the performance across various `output_window` and `exchange_window` combinations.
- **Equity Line Plot**: Shows cumulative returns over time for the optimal trading strategy.

## Setup & Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/yourprojectname.git
   cd yourprojectname
