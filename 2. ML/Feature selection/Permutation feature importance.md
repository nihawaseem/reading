- Randomly shuffling the values of a single feature and observing the resulting degradation of the model’s score
- Model-agnostic
- Can be calculated multiple times to provide a variance 
- Does not reflect the intrinsic predictive value of a feature by itself but **how important this feature is for a particular model**
- Using a held-out set makes it possible to highlight which features contribute the most to the generalization power of the inspected model. Features that are important on the training set but not on the held-out set might cause the model to overfit.

#### Algorithm
- **Inputs:** model and dataset
- Compute score (chosen metric) of the model on data
- 