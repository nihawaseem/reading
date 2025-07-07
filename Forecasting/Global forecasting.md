- **Local approach**: standard univariate time series forecasting problem - assuming each time series comes from a different data generating process so it should be modelled individually 

### Global/cross-learning approach
- Exploits the natural scenario where all series in the set are similar
- Introduce a strong assumption of all the time series in the set coming from the same process 
- Pools data of all series together and fits a single univariate forecasting function 

#### Takeaways of paper
1. A local algorithm might learn a different function to forecast each series in the set, but its forecasts **can always be replicated** by a single function learnt by a global algorithm
2. Generalisation bounds of local and global algorithms for forecasting sets of time series
	- Model complexity: number of functions that can be fit to data
	- Sample size
	- Difference between training (in-sample) error and testing (out of sample) error
	- Bounds are agnostic of model and data distribution 
3. Motivate the use of global algorithms with large complexity - complexity increased by:
	- Adding features
	- Increasing the memory/order of autoregression
	- Partitioning 

“Each forecast that can be expressed by a local algorithm can also be expressed by a global algorithm.”

### Equivalence of local and global algorithms for time series forecasting 
1. $A_L$ - set of all local learning algorithms
2. $A_G$ - set of all global learning algorithms 

### Local benchmarks 
- Auto ARIMA
- ets
- theta
- TBATS
- STL-AR

### Global methods
1. Linear autoregressive (can be considered a baseline)
2. Featurized linear autoregressive - linear model fit by least squares with increased complexity by adding nonlinear features in the form of polynomials of degree 2 and 3
3. Deep network autoregressive 
4. Regression tree autoregressive 
5. Partitioned linear 


#### Errors
- MASE: a popular scale-free error measure which rarely divides by 0   

### Increasing memory of models
- Longer memory leads global linear models to outperform local![[Pasted image 20250707094121.png]]
- The pattern of improving accuracy when increasing memory holds for the majority of datasets. At very long memories, we see some form of convergence in accuracy until the error explodes because even the global model gets into an over-fitting regime. This behavior is exemplified in the hospital dataset, Figure 19, but would happen for all datasets when the potential maximum memory is much larger than the number of series in the set. This type of over-fitting can be prevented in practice by simple **cross-validation or regularization**.
- Global models fit long memory patterns - global models pick seasonality patterns without prior knowledge 


Model complexity vs memory In terms of the effect of memory we highlight two phenomena. The main is that both sources of complexity, memory and model class, are effective at improving forecast accuracy. When both are included, model class interacts with memory in different ways depending on the dataset, but in general a more complex model class requires less memory to achieve the same level of accuracy than the more simple class.