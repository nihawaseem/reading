- lists: O(n) lookup
- tuples: immutable. faster than lists for lookup
- dictionaries: O(1) lookup
- sets: values have to be unique

- numpy arrays: 
	- 2d arrays

- arrays in ML:
	- convert to tensorflow tensor format, or pytorch tensor format
	- use pytorch and tensorflow profiler for figuring out bottlenecks in code

- pandas
	- vectorized string operations: lower, strip, split, etc
	- you can also use .apply()