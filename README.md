# Gold Price Time Series Analysis and Forecasting

Time series analysis and forecasting of daily gold prices (MCX market) in R.

## Objective
Forecast the closing price of gold to support investment and risk management,
market insight, and business and policy decision-making.

## Data
- Daily gold prices from the MCX market
- Variables: Date, Close Price, Open, High, Low, Volume, % Change
- Target variable: Close Price

## Methodology
1. **Exploration:** time series plot, additive decomposition, ACF and PACF
2. **Stationarity tests:** Augmented Dickey-Fuller (p = 0.5077) and KPSS (p = 0.01),
   both indicating a non-stationary series
3. **Differencing** to remove the trend
4. **Modeling:** ARIMA(4,0,5) and ETS(A,N,N) fitted on a training subset
5. **Evaluation and forecasting:** model comparison with RMSE, MAE, MASE,
   then 90-day and 12-month forecasts

## Results
| Model | RMSE | MAE | MASE |
|---|---|---|---|
| ARIMA(4,0,5) | 368.53 | 249.06 | 0.687 |
| ETS(A,N,N) | 370.28 | 249.16 | 0.687 |

- The series is clearly non-stationary and needs differencing.
- ARIMA(4,0,5) was selected, with a slightly lower RMSE than ETS.
- The two models perform very similarly, and the forecast leaves room for improvement.

## Repository structure
- `Code/`: R Markdown file with the full analysis
- `Report/`: HTML report with code and outputs (download to view in a browser)
- `Presentation/`: PDF presentation of the results

## Tools
R (forecast, tseries, ggplot2)
