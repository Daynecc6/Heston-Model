# Option Pricing Using the Heston Model

## Overview
This project explores option pricing through the development and implementation of the Heston model, a sophisticated approach to modeling stochastic volatility in financial markets. The project was conducted as part of a quantitative finance and deep learning course, aiming to price options on the S&P 500 index.

## Introduction
The Heston model is chosen for its rigorous mathematical foundation and its ability to capture the dynamic nature of financial markets. Initially, the goal was to train the model on American SPY options, but due to computational complexities, the focus shifted to European SPX options.

## Methodology

### Mathematical Framework
- **Stock Price Dynamics**: Modeled using a stochastic differential equation (SDE).
- **Volatility Dynamics**: Modeled using a Cox-Ingersoll-Ross (CIR) process.

### Implementation Using QuantLib
- **Heston Process Setup**: Configured with market data and optimized parameters.
- **Analytic Heston Engine**: Utilized for efficient and accurate option pricing using Fourier transform techniques.

### Parameter Optimization
- **Objective Function**: Defined to measure the squared errors between predicted and actual market prices.
- **Optimization Technique**: Employed `scipy.optimize.minimize` with the 'L-BFGS-B' method to refine model parameters.

### Data Acquisition and Preprocessing
- **Option Data**: Fetched using the `yfinance` library for S&P 500 index options.
- **Spot Price**: Retrieved for the latest trading day.
- **Volume and Price Filtering**: Ensured data quality by filtering options with low trading volumes and prices.
- **Handling Expiration Dates**: Standardized by converting to numerical values representing maturity in years.
- **Risk-Free Rates**: Scraped from the U.S. Treasury website and fitted using the Nelson-Siegel-Svensson model.

## Results

### Visual Comparisons of Predicted and Actual Prices
An interactive 3D scatter plot provides a comprehensive visual comparison, highlighting model performance and identifying discrepancies.
![image](https://github.com/Daynecc6/Heston-Model/assets/103780036/104e6df1-447d-4999-b152-0f716fd3c33b)

### Statistical Analysis
- **Mean Absolute Error (MAE)**: 26.51
- **Mean Squared Error (MSE)**: 2715.98
- **Root Mean Squared Error (RMSE)**: 52.12
- **Correlation Coefficient**: 0.981

### Residual Analysis
A residuals plot shows the differences between actual and predicted prices, indicating that most errors are random with some outliers.

## Conclusion
The Heston model effectively captures overall market trends but requires further refinement to handle outliers and extreme market conditions. Future work could focus on adjusting model parameters, incorporating additional market factors, or exploring more complex stochastic models.

## Dependencies
- Python 3.x
- Jupyter Notebook
- QuantLib
- Numpy
- Scipy
- Pandas
- Matplotlib
- yfinance
