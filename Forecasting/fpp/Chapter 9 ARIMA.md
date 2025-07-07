## Chapter 9 - ARIMA

### Random walk model

- $y_t = y_{t-1} + \epsilon_t$
- Typically have long periods of apparent trends up or down
- Sudden and unpredictable changes in direction
- **Naive forecast: $\hat{y}_{T+h|T} = y_T$**

### Differencing

- Transform a time series to stabilize variance → remove changes in the level and hence eliminate/reduce trend and seasonality
- Test for stationarity (i.e. no differencing required) using the **unit root test**

### **Autocorrelation and ACF**

- Measures the linear relationship between _lagged values_ of a time series
- e.g. $r_1$ is an autocorrelation coefficient and measures the relationship between $y_t$ and $y_{t-1}$

**ACF**

- $r_1...r_T$ are plotted to show the autocorrelation function (ACF)/correlogram
- Interpreting trend and seasonality
    - **Trend**: autocorrelations for small lags tend to be large and positive. As lags increase positive values would decrease.
    - **Seasonality**: autocorrelations will be larger for the seasonal lags (at multiples of the seasonal frequency) than for other lags

**PACF**

- Measure the relationship between $y_t$ and $y_{t-k}$ after removing the effects of lags $1, 2, 3...k-1$

### Autoregressive models

- Forecast the variable of interest using a linear combination of _past values of the variable._ i.e. it’s a regression of the variable against itself
- Autoregressive model of order $p, AR(p)$:

$$ yt=c+ϕ_1yt−1+ϕ_2yt−2+⋯+ϕ_pyt−p+ε_t $$

- $\epsilon_{T} \sim N(0,1)$ (white noise). Variance of the error term $\epsilon_t$ will only change the scale of the series, not the patterns.
- When $\phi_1 = 1, c\neq 0, y_t$ is equivalent to a random walk with **drift**
- When $\phi_1 < 0, y_t$ tends to oscillate around the mean

**Parameters**

- $AR(1): -1 < \phi_1 < 1$
- $AR(2): -1 < \phi_2 < 1, \phi_1 + \phi_2 < 1, \phi_2 - \phi_1 < 1$

### Moving average model

- Uses past forecast errors in a regression-like model
- $MA(q)$ model:

$$ y_t=c+ε_t+θ_1ε_{t−1}+θ_2ε{t−2}+⋯+θ_qε_{t−q} $$

- The value of $\phi_1^k$ gets smaller as $k$ gets larger
- $MA(\infty)$ model:

$$ y_t=\epsilon_t+\phi_1\epsilon_{t−1}+\phi_1^2\epsilon_{t−2}+\phi_1^3\epsilon_{t−3}+⋯, $$

### Non-seasonal ARIMA model

$$ y_t'=c+\phi_1y_{t−1}'+ ⋯+ϕ_py_{t−p}'+θ_1ε_{t−1}+⋯+θ_qε_{t−q}+ε_t $$

$ARIMA(p, d, q):$

- **p:** order of the autoregressive part
- **d:** degree of first differencing involved
- **q:** order of the moving average

**Special cases of ARIMA**

|White noise|ARIMA(0, 0, 0)|
|---|---|
|Random walk|ARIMA(0, 1, 0) with no constant|
|Random walk with drift|ARIMA(0, 1, 0) with a constant|
|Autoregression|ARIMA(p, 0, 0)|
|Moving average|ARIMA(0, 0, q)|

|Order|Long-term forecast|
|---|---|
|c=0 and d=0|will go to zero|
|c=0 and d=1|will go to a non-zero constant|
|c=0 and d=2|will follow a straight line|
|c≠0 and d=0|will go to the mean of the data|
|c≠0 and d=1|will follow a straight line|
|c≠0 and d=2|will follow a quadratic trend|

### Fitting an ARIMA model with fpp

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/67cdd60d-118b-453f-8dd5-ab9f77664867/f9b176d6-e46c-4807-b0e2-5e8b2051c60d/Untitled.png)

## EDA

- time plot - check for seasonality
- seasonal plot - e.g. if the data has monthly seasonality overlay each month
    - use for feature engineering
- exogenous variable?