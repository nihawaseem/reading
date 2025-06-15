- Test-driven development (TDD) is a software development process where a developer
writes the tests before writing the functions that actually achieve the objectives of the
project. The aim is to use the tests to describe the requirements of the code, and the
tests specify the expected behavior and the function’s inputs and outputs. Then, the
developer writes code to pass the test. This encourages developers to make their code
modular and break down complex problems into easily testable pieces.

- Keep tests in a separate folder and start the names of the python files containing tests with \_test 
- Libraries: Faker for data generation, Hypothesis for finding edge cases where code doesn't work 
- Testing frameworks: pytest, unittest, tox
- Test coverage: proportion of the lines of code in a file that is executed when all tests are run

### Types of tests
1. Unit tests
2. Integration test
3. Acceptance test
4. Load test
5. Security test
6. Usability test

### Data validation
- Pandera
- Pydantic 
- Great Expectations

### Testing for ML
- Test model inference with different inputs 

https://www.jeremyjordan.me/testing-ml/
- always write tests for newly introduced logic when contributing code,
- when contributing a bug fix, be sure to write a test to capture the bug and prevent future regressions.
![[Pasted image 20250612225024.png]]


![[Pasted image 20250612225105.png]]


### Model evaluation and model testing
- **Model evaluation** covers metrics and plots which summarize performance on a validation or test dataset.
- **Model testing** involves explicit checks for behaviors that we expect our model to follow.

### Writing model tests
- Pre-train tests: identify some bugs early on and short-circuit a training job

### Post-train tests
1. Invariance tests:
	- allow us to describe a set of perturbations we should be able to make to the input _without_ affecting the model's output
	- We can use these perturbations to produce pairs of input examples (original and perturbed) and **check for consistency** in the model predictions
2. Directional expectation tests:
	- allow us to define a set of perturbations to the input which _should_ have a _predictable_ effect on the model output
	- ![[Pasted image 20250612225613.png]]
3. **Minimum Functionality Tests**:
	- identify critical scenarios where prediction errors lead to high consequences

- For ML model testing, it is recommended to structure your tests around the "skills" you expect the model to acquire while learning to perform a given task

**Model development pipeline**
![[Pasted image 20250612225916.png]]
