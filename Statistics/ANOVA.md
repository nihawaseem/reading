#### Testing for model relevance 
- Null hypothesis: $H_0: \beta = 0$, $H_1: \beta \neq 0$ 
- If $\beta = 0$, $\textbf{y} =\epsilon$ consists entirely of errors. Hence $\textbf{y}^T\textbf{y}$ is the sum of squares of the errors and measures the variability of the errors
- If $\beta \neq 0$, $\textbf{y} = X\beta + \epsilon$ . Hence some of $\textbf{y}^T\textbf{y}$ comes from errors and but some come from the model predictions. 

##### Variation in the response variable
$SS_{Total} = SS_{Reg} + SS_{Res}$
- regression sum of squares: variation in the response variable explained by the model
- residual sum of squares: variation attributed to error 
- **Two extremes:** 
	- $y=X\beta$ so $SS_{Res} = 0$ (under H1)
	- $y=\epsilon$ so $SS_{Reg} = 0$ (under H0)

![[Pasted image 20240601141725.png]]
##### Testing if $\beta = 0$ 
- Under $H_0$: 
$\frac{MS_{Reg}}{MS_{Res}} \sim F(p,n-p)$ 

- If $\