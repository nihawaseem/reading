#### Overview
- To make great products, do machine learning like the great engineer you are, not like the great machine learning expert you aren’t

#### Before Machine Learning
1. ==Don't be afraid to launch a product without machine learning - use heuristics== 

2. ==Before setting up a **new system with ML** track what's going on in the current system (which does not have ML) **with liberal use of metrics**==
	- Get historic data
	- Understand what works and what doesn't work. e.g. For instance, suppose you want to directly optimize one­-day active users. However, during your early manipulations of the system, you may notice that dramatic alterations of the user experience don’t noticeably change this metric
	- For instance, suppose you want to directly optimize one­-day active users. However, during your early manipulations of the system, you may notice that dramatic alterations of the user experience don’t noticeably change this metric
	
3. ==Choose machine learning over a **complex heuristic**== 
	

#### Phase 1: your first pipeline
- get the training data into the learning system
- get any metrics of interest instrumented
- create a serving infrastructure

4. ==Keep the first model simple and get the infrastructure right==. Infrastructure should include:
		- how to get training data to the algorithm
		- define what "good" and "bad" mean to the system
		- how to integrate your model into the application 
	Choosing simple features means:
		- features reach training stage correctly
		- model learns reasonable weights
		- features reach model in server correctly
	Simple model provides you with baseline metrics and  behaviour. 
	Some teams aim for a "neutral" first launch: a first launch that explicitly de­prioritizes machine learning gains, to avoid getting distracted.
	
5. ==Test the infrastructure independently from the machine learning==
	- Test getting data into the algorithm
	- Test getting models out of the training algorithm 
	- Add tests for code in training and serving environments 
	
6. ==Be careful about dropped data when copying pipelines== 
	- When you copy pipelines, the old pipeline drops data you need for the new pipeline 
	
7. ==Turn heuristics into features, or handle them externally 
	- Existing heuristics (solutions for problems) can give you a boost when developing your model. They can be tweaked for extra gains. Things you can do with heuristics:
		- **Preprocess using the heuristic**. For example, if, in a spam filter, the sender has already been blacklisted, don’t try to relearn what "blacklisted" means. Block the message. This approach makes the most sense in binary classification tasks.
		- **Create a feature:** For example, if you use a heuristic to compute a relevance score for a query result, you can include the score as the value of a feature. Later on you may want to use machine learning techniques to massage the value (for example, converting the value into one of a finite set of discrete values, or combining it with other features) 
		- **Mine the raw inputs of the heuristic:** Feed inputs into the learning separately 
		- **Modify the label:** If the heuristic captures info not currently contained in the label, you could modify your label 
##### Monitoring 
8. ==Know the freshness requirements of your system: understand how performance degrades if you have a model that is using old features 

9. ==Detect problems before exporting models: do sanity checks by:
	- Checking area under ROC curve before exporting 
	
10. ==Watch for silent failures 
	- E.g. Maybe there is no data being populated during a join that reduces feature column population 
	- Track statistics of the data and manually inspect on occasion to reduce this
	
11. ==Give feature columns owners and documentation 
	 - Descriptive names and how it is expected to help

##### First objective 
12. ==Don't over think about which objective you choose to directly optimise
	- Don't think about balancing different metrics when you can still easily increase all of the metrics 
	
 13. ==Choose a simple, observable, and attributable metric for your first objective 
	 - Should be a proxy for the "true" objective
	 - Direct: was this ranked link clicked, etc
	 - Indirect: did the user visit the next day, etc 
	 - Don't get the machine learning to figure out: is the user happy or satisfied, how will this affect the company's overall health 

14. ==Starting with an interpretable model makes debugging easier
	- Probabilistic models are easier to debug than models that try to optimize classification accuracy or ranking performance 
	- If probabilities in training deviate from probabilities predicted in side­-by-­sides or by inspecting the production system, this deviation could reveal a problem

15. ==Separate spam filtering and quality ranking in a policy layer== 
#### Phase 2: feature engineering
- after we have a working end to end system with unit and system tests instrumented 
-  pulling in as many features as possible and combining them in intuitive ways

16. ==Plan to launch and iterate 
	- You are coming up with new features
	- You are tuning regularisation and combining old features in new ways
	- You are tuning the objective 

17. ==Start with directly observed and reported features as opposed to learned features 
	- **Learned feature:** feature generated either by an external system (such as an unsupervised clustering system) or by our learner (factored model or deep learning, e.g.). Don't put them in the first model. 
 		 If you use an external system to create a feature, remember that the external system has its own objective. The external system's objective may be only weakly correlated with your current objective. If you grab a snapshot of the external system, then it can become out of date. If you update the features from the external system, then the meanings may change. If you use an external system to provide a feature, be aware that this approach requires a great deal of care. The primary issue with factored models and deep models is that they are non­convex. Thus, there is no guarantee that an optimal solution can be approximated or found, and the local minima found on each iteration can be different. This variation makes it hard to judge whether the impact of a change to your system is meaningful or random. By creating a model without deep features, you can get an excellent baseline performance. After this baseline is achieved, you can try more esoteric approaches.

18. ==Explore with features of content that generalize across contexts 

19. ==Use very specific features when you can==
	With tons of data, it is simpler to learn millions of simple features than a few complex features. Identifiers of documents being retrieved and canonicalized queries do not provide much generalization, but align your ranking with your labels on head queries. Thus, don’t be afraid of groups of features where each feature applies to a very small fraction of your data, but overall coverage is above 90%. You can use regularization to eliminate the features that apply to too few examples.

20. ==Combine and modify existing features to create new features in human-understandable ways 
	- **Discretisation:** taking a continuous feature and creating many discrete features from it 
	- **Crosses:** combine two or more feature columns (with Tensorflow feature column)

21. ==The number of feature weights you can learn in a linear model is roughly proportional to the amount of data you have 

22. ==Clean up features you are no longer using
	- Keep your infrastructure clean 
	- Keep coverage in mind when considering what features to add or keep 
	- Some features punch above their weight - if you have a feature which covers only 1% of the data, but 90% of the examples that have the feature are positive, then it will be a great feature to add

##### Human analysis of the system
23. ==You are not a typical end user
	- **fishfooding:** using a prototype within your team
	- **dogfooding:** using a prototype within your company 
	- use user experience methodologies - create user personas and do usability testing

24. ==Measure the delta between models==
	- Calculate how different the results of the new model are from results of production model 
	- If the difference is small, you can tell without running an experiment that there will be little change
	- If the difference is large, you want to make sure the change was good 

25. ==When choosing models, utilitarian performance trumps predictive power== 

26. ==Look for patterns in the measured errors and create new features==
	- Give the model a feature that allows it to fix the error it made
	- Once you have examples that the model got wrong, look for trends that are outside your current feature set

27. ==Try to quantify observed undesirable behaviour
	- rule: **measure first, optimise second**

28. ==Identical short-term behaviour does not imply long-term behaviour 

##### Training-serving skew
- A discrepancy between how you handle data in the training and serving pipelines.
- A change in the data between when you train and when you serve.
- A feedback loop between your model and your algorithm.

29. Train like you serve: save the set of features used at serving time, and then pipe those features to a log to use them at training time 
		Do this to verify consistency between serving and training

30. Don't arbitrarily drop data

31. If you join data from a table at training and serving time, the data in the table may change
	- Log features at serving time

32. Re-use code between training pipeline and serving pipeline whenever possible 

33. If you produce a model based on data from $t_1...t_3$ test the model on data from $t_4$ onwards 

34. Make small short-term sacrifices in performance for very clean data

#### Phase 3: slowed growth, optimisation refinement, and complex models 

#### Phase 4: reaching a plateau 