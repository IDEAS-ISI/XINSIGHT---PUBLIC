
# Time Series Forecasting – User Guide

This guide explains how to use the **Time Series Forecasting** feature available in the **Storytelling** module.

---

## Overview

The Time Series Forecasting module helps users predict future values based on historical data. The platform supports forecasting using:

* Prophet Model
* Holt's Exponential Smoothing (Holt's ES)
* Simple Exponential Smoothing (SES)

The system visualizes both historical and forecasted values.

---

## Step 1: Open the Storytelling Module

1. From the left navigation panel, click **Storytelling**.
2. The Storytelling workspace will open.

---

## Step 2: Select a Dataset

1. At the top of the page, locate the **Select a Dataset** dropdown.
2. Choose the dataset you want to analyze.

After selection, the platform loads the dataset and enables forecasting options.

---

## Step 3: Open the Time Series Tab

1. Navigate to the available tabs:

   * Measures and Dimensions
   * Chart Recommendations
   * Charts
   * Time Series
2. Click **Time Series**.

The forecasting interface will appear.

---

## Step 4: Select the Date Column

1. Locate **Select the Date Column**.
2. Choose the column that contains date or timestamp information.

---

## Step 5: Select the Forecast Variable

1. Locate **Select the Column Which Is to Be Forecasted**.
2. Choose the numeric column you want to predict.

### Examples

* Sales
* Revenue
* Quantity Sold
* Temperature
* Stock Price

---

## Step 6: Select Forecast Frequency

Choose the forecasting frequency based on your data.

Supported frequencies:

* Year
* Month
* Week
* Day
* Hour

### Available Options

| Option | Description      |
| ------ | ---------------- |
| Y      | Yearly Forecast  |
| M      | Monthly Forecast |
| W      | Weekly Forecast  |
| D      | Daily Forecast   |
| H      | Hourly Forecast  |

---

## Step 7: Select Forecasting Model

Choose the forecasting algorithm that best suits your data.

### Prophet Model

#### Used For

* Forecasting data with trend, seasonality, and holiday effects
* Continuous numerical data with complex patterns
* Time series containing yearly, monthly, weekly, or daily seasonal behavior

#### Best Suited For

* Retail sales forecasting
* Website traffic prediction
* Energy consumption forecasting
* Business metrics influenced by holidays or special events

#### Key Advantages

* Automatically detects trends and seasonality
* Handles missing values effectively
* Works well with irregularly spaced time series data
* Provides confidence intervals for forecasts

#### Example

If coffee sales increase during weekends and specific holidays while also showing long-term growth, the Prophet model can capture these patterns and generate more accurate forecasts.

---

### Holt's Exponential Smoothing (Holt's ES)

#### Used For

* Trend-based forecasting
* Continuous numerical data
* Time series with increasing or decreasing patterns

#### Best Suited For

* Sales data with consistent upward or downward trends
* Revenue forecasting
* Demand forecasting with gradual growth or decline
* Business metrics showing long-term directional movement

#### Key Advantages

* Captures trend information effectively
* Gives more importance to recent observations
* Simple and computationally efficient
* Suitable for datasets without strong seasonality

#### Example

If monthly sales have been steadily increasing over the past few years, Holt's Exponential Smoothing can model the trend and forecast future sales based on that growth pattern.

---

### Simple Exponential Smoothing (SES)

#### Used For

* Forecasting data with no clear trend or seasonality
* Continuous numerical data
* Time series where values fluctuate around a relatively constant average

#### Best Suited For

* Stable sales data
* Inventory levels
* Daily demand with minimal variation

#### Key Advantages

* Simple and easy to implement
* Gives higher weight to recent observations
* Effective for stable datasets
* Requires minimal parameter tuning

#### Example

If monthly sales remain fairly consistent over time without increasing or decreasing trends, SES can provide reliable forecasts by giving more weight to recent observations.

---

## Step 8: Specify Forecast Horizon

Enter the number of future periods to predict.

### Example

If the value entered is **2**, the system forecasts the next **2 periods** based on the selected frequency.

### Forecast Horizon by Frequency

| Frequency | Forecast Horizon Example |
| --------- | ------------------------ |
| Yearly    | Next 2 Years             |
| Monthly   | Next 2 Months            |
| Weekly    | Next 2 Weeks             |
| Daily     | Next 2 Days              |
| Hourly    | Next 2 Hours             |

---

## Step 9: Generate Forecast

1. Click the **Predict** button.
2. The platform trains the selected forecasting model using historical data.
3. Future predictions are generated automatically.

---

## Step 10: View Forecast Visualization

The platform automatically generates a chart displaying:

### Original and Forecasted Data

The visualization contains:

* Historical data
* Forecasted values
* Trend continuation

### Benefits

Users can:

* Compare past and future values
* Identify trends
* Understand expected future behavior
<p align="center">
  <img src="images/actual-vs-fitted.png" width="900">
</p>
---

## Summary

The Time Series Forecasting module enables users to generate forecasts using industry-standard forecasting techniques, including Prophet, Holt's Exponential Smoothing, and Simple Exponential Smoothing. By selecting the appropriate dataset, date column, target variable, frequency, model, and forecast horizon, users can quickly generate meaningful future predictions and visualize expected trends.
