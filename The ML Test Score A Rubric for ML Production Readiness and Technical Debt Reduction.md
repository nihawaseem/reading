- test rubric, which is based on engineering decades of production- level ML systems at Google, in systems such as ad click prediction [2] and the Sibyl ML platform [3].
- Each test is written as an assertion; our recommendation is to test that the assertion is true, the more frequently the better, and to fix the system if the assertion is not true.

- Machine learning systems differ from traditional software- based systems in that the behavior of ML systems is not specified directly in code but is learned from data

![[Pasted image 20250721162509.png]]


1. Feature expectations are captured in a schema - feature tests
2. All features are beneficial
3. No feature’s cost is too much
4. Features adhere to meta-level requirements
5. New features can be added quickly: The faster a team can go from a feature idea to the feature running in production, the faster it can both improve the system and respond to external changes. For highly efficient teams, this can be as little as one to two months even for global-scale, high-traffic ML systems. Note that this can be in tension with Data 5, but privacy should always take precedence.
6. All hyperparameters have been tuned
7. The impact of model staleness is known
8. A simpler model is not better (check against baselines)