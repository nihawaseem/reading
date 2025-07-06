- **Local approach**: standard univariate time series forecasting problem - assuming each time series comes from a different data generating process so it should be modelled individually 

### Global/cross-learning approach
- Exploits the natural scenario where all series in the set are similar
- Introduce a strong assumption of all the time series in the set coming from the same process 
- Pools data of all series together and fits a single univariate forecasting function 

#### Takeaways of paper
1. A local algorithm might learn a different function to forecast each series in the set, but its forecasts can always be replicated by a single function learnt by a global algorithm
2. Generalisation bounds of local and global algorithms for forecasting sets of time series
