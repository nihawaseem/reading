- Objectives 
	- Name all objectives of an MLproject. Some objectives may be in conflict with each other
	- **Quality loss:** the difference between each post’s predicted quality and its true quality
- Recommender systems: customer's predicted revenue and actual revenue - changes due to pushed features?
	- Pareto optimization
- ACID
	- Atomicity
To guarantee that all the steps in a transaction are completed successfully as a group. If any step in the transaction fails, all other steps must fail also. For example, if a user’s payment fails, you don’t want to still assign a driver to that user.
Consistency
To guarantee that all the transactions coming through must follow predefined rules. For example, a transaction must be made by a valid user.
Isolation
To guarantee that two transactions happen at the same time as if they were isolated. Two users accessing the same data won’t change it at the same time. For example, you don’t want two users to book the same driver at the same time.
Durability
To guarantee that once a transaction has been committed, it will remain committed even in the case of a system failure. For example, after you’ve ordered a ride and your phone dies, you still want your ride to come.

However, transactional databas”

Excerpt From
Designing Machine Learning Systems
Chip Huyen
This material may be protected by copyright.

- Modes of dataflow:
	- Through databases
	- “Data passing through services using requests such as the requests provided by REST and RPC APIs (e.g., POST/GET requests)
Data passing through a real-time transport like Apache Kafka and Amazon Kinesis”

Excerpt From
Designing Machine Learning Systems
Chip Huyen
This material may be protected by copyright.

“The most popular styles of requests used for passing data through networks are REST (representational state transfer) and RPC (remote procedure call). Their detailed analysis is beyond the scope of this book, but one major difference is that REST was designed for requests over networks, whereas RPC “tries to make a request to a remote network service look the same as calling a function or method in your programming language.” Because of this, “REST seems to be the predominant style for public APIs. The main focus of RPC frameworks is on requests between services owned by the same organization, typically within the same data center.”

Excerpt From
Designing Machine Learning Systems
Chip Huyen
This material may be protected by copyright.