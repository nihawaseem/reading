##### Standardized residuals
- $e_i = y_i - X\beta$ 
- $z_i = \frac{e_i}{\sqrt{s^2(1-H_{ii})}}$ 
- hat matrix converts observed responses into estimated responses: $\hat{y} = Hy$ 

##### Leverage
- if $H_{ii}$ is particularly large, $y_i$ has a large effect on the model's fit
- this is defined as leverage of point i
- a point with a large leverage combined with a large residual may distort the fit 

##### Cook's distance
- large if both the standardized residual and the leverage is large
- considered large if >1 and small if <0.5

##### Residuals vs fitted values
Look for:
- points with large residual (unequal variances)
- a trend in the residuals (bias)
- a pattern in the residuals (correlation)

##### Normal QQ plot
Look for:
- a small number of outliers
- over or under-estimation in the tails
- skewness

##### Square root of absolute values of standardized residuals vs fitted values
Look for:
- points with high residuals (unequal variance)
- trends in the size of the residuals (heteroskedasticity) 

##### Leverage vs standardized residuals 
Look for:
- points with high residual (unequal variance)
- points with high leverage (potentially dangerous)
- points with high Cook's distance (poor fit)
- pattern in the residuals (correlation)