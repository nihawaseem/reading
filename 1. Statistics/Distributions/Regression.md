#### The full rank model
- $y = X\beta + \epsilon$  
- $\epsilon \sim MVN(0, \sigma^2I)$     
- $r(X) = k+1$ where k is the number of design variables. Hence $X^TX$ is invertible
- Least squares estimation: minimizing the sum of the squares of the residuals

##### Interval estimates for parameters 
- $\textbf{b} \sim MVN(\beta, (X^TX)^{-1}\sigma^2)$  
- $\frac{SS_{Res}}{\sigma^2} \sim \chi^2(n-p)$    
- Using a t distribution with n-p degrees of freedom, $b_i \pm t_{\alpha/2}s\sqrt{c_{ii}}$  
- Covariance matrix: $c = (X^TX)^{-1}$ , so the variance of $b_{i}$ is $c_{ii}$ 
- 

##### Prediction intervals
- **Confidence interval:** Given a set of inputs, a 95% confidence interval for the response gives an ==interval that contains the expected response 95% of the time==.
- **Prediction interval:** In contrast, given a set of inputs, a 95% prediction interval produces an ==interval in which we are 95% sure that any given response with those inputs lies in==.