- **...premature optimization is the root of all evil (or at least most of it) in programming.**
- Compiling python: 
	- You may be able to get your code to run faster by compiling Python to a lowerlevel
language using tools like Cython, Numba, and PyPy.
- Numba contains a subset of Python;
Cython is a superset of Python with additional options in C; and PyPy is a reimplementation
of Python using just-in-time compilation.
- **Just-in-time compilation:** code is compiled during execution of a program rather than before execution
- Parallel and distributed computing: 
	- Parallel: running code on more than one processor within one computer
	- Distributed: running code on multiple different machines at the same time

### Profiling code
- cProfile
- snakeViz
- line_profiler
- Memray for memory usage monitoring

### Big O notation
- O: order/growth rate of the function 
- **O(1):** constant time, runtime independent of dataset size
- O(n): runtime increases linearly w dataset size
- O(n^2): quadratic time, runtime increases proportionally w square of dataset size 