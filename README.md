# Forecasting with Prophet README

This repository contains a Python script for forecasting call volumes using Facebook's Prophet library, utilizing historical call data stored in a Snowflake database. The script performs data preprocessing, outlier handling, holiday adjustment, and forecasting to generate accurate predictions for future call volumes.

## Prerequisites

- Python 3.x
- Required Python libraries: `pyodbc`, `pandas`, `holidays`, `numpy`, `prophet`

## Setup

1. Install the required Python libraries using pip:

   ```
   pip install pyodbc pandas holidays numpy prophet
   ```

2. Ensure access to a Snowflake database with historical call data.

## Usage

1. Update the Snowflake DSN (Data Source Name) in the script with your Snowflake configuration:

   ```python
   dsn_name = "mysnowflake"
   ```

2. Run the script:

   ```bash
   python forecast_calls.py
   ```

3. After execution, the forecast results will be saved to a CSV file named `forecast_results.csv`.

## Script Overview

1. **Establish Database Connection**: Connect to the Snowflake database to retrieve historical call data.

2. **Retrieve Historical Data**: Fetch historical call data from the database and preprocess it for analysis.

3. **Retrieve Canada Holidays**: Retrieve Canadian holidays including provincial holidays and Easter Sunday/Monday for the forecast period.

4. **Data Preprocessing**: Perform data preprocessing tasks such as converting data types, adding date-related features, and renaming columns.

5. **Handling Outliers**: Adjust outliers in the call volume data based on weekday percentiles.

6. **Applying Weighted Average**: Calculate a weighted rolling mean of call volumes to smooth out fluctuations.

7. **Forecasting with Prophet**: Use Facebook's Prophet library to forecast future call volumes.

8. **Factoring in Holidays**: Incorporate holiday effects into the forecast model.

9. **Predicting Future Data**: Generate predictions for future call volumes.

10. **Handling Holiday Adjustments**: Adjust forecasted call volumes based on holiday factors.

11. **Additional Data Analysis**: Calculate daily, weekly, and monthly variances and accuracies of the forecasts.

12. **Export Forecast Results**: Save the forecast results to a CSV file for further analysis.

## Customization

- Adjust the forecast period and frequency by modifying the `periods` and `freq` parameters in the `make_future_dataframe` function.
  
- Define specific adjustments for holidays and dates in the script as needed.

## Note

- Ensure that the Snowflake database connection details are correctly configured before running the script.

- Review and customize the holiday adjustment factors and date adjustments according to your specific requirements.


