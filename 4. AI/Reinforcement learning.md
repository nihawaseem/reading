#### Components
1. Agent
2. Environment - the world the agent lives in. At every step of interaction, the agent sees a (possibly partial) observation of the state of the world, and then decides on an action to take. The environment changes when the agent acts on it, but may also change on its own.
3. Reward - a number that tells it how good or bad the current world state is
4. Return -  the goal of the agent is to maximise its cumulative reward, called **return** 

#### States and observations
- **State** $s$: a complete description of the state of the world
- **Observation** $o$: a partial description of a state. Agent can either full observe the environment (state) or partially observe it 

#### Action spaces
- **Action space**: the set of all valid actions in a given environment 
- **Discrete action spaces:** only a finite number of moves are available to the agent
- **Continuous action space**: actions are real valued vectors 

#### Policies
- **Policy:** a rule used by an agent to decide what actions to take 
- Can be deterministic, where $a_t = \mu(s_t)$ or stochastic, where $a_t \sim \pi(\cdot|s_t)$  
	- Deterministic - action is a function of state
	- Stochastic: action follows the distribution of something ? given state
- **Parametrised policies:** 
	- These policies' outputs are computable functions that depend on a set of parameters 
	- Parameters of a policy: $\theta$ 
		- $a_t = \mu_{\theta}(s_t)$ 
		- $a_t \sim \pi_{\theta}(\cdot | s_t)$ 

#### Stochastic policies
- **Categorical policies** for discrete action spaces 