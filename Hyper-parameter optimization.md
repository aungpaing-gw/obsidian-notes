## Hyperparameter Optimization
two types of parameters exist in machine learning models: one that can be initialized and updated through the data learning process (eg. the weights of neurons in neural network.) named model parameters; while the other, named hyper-parameters, cannot be directly estimated from data learning and must be set before trainning a ML model because they define the architecture of a ML model.

To build an optimal ML model, a range of possibilities must be explored. The process of designing the ideal model architecture with an optimal hyper-parameters configuration is named hyper-parameter tuning. Hyper-parameters are different in each model, that including categorical, discrete, and continuous. The main aim of HPO is to automate hyper-parameter tuning process and make it possible for users to apply machine learning models to practical problems effectively.

Traditional optimization techniques may be unsuitable for HPO problems, since many HPO problems are non-convex or non-differentiable optimization problems, and may result in a local instead of global optimum.

Compared with traditional optimization methods like gradient descent, many other optimization techniques are more suitable for HPO problems, including decision-theoretic approaches, Bayesian optimization models, multi-fidelity optimization techniques, and metaheuristics algorithms.

### Decision-Theoretic approaches
Decision-theoretic methods are based on the concept of defining a hyper-parameter search space and then detecting the hyper-parameter combination in the search space, ultimatley selecting the best-performing hyper-parameter combination.
- **Grid search ( GS  )**
- **Random search ( RS )**

### Bayesian optimization
Unlike GS and RS, Bayesian optimization models determine the next hyper-parameter value based on the previous results of tested hyperparameter values, which avoid many unnecessary evaluation. To be applied to different problems, BO can model the distribution of the objective function using different models as the surrogate function, including GP, TPE and RF. Thus, BO can detect the optimal hyper-parameter combination within fewer iterations than GS and RS.
Bayesian Optimization is an iterative algorithm that is popularly used for HPO problems. To determine the next hyper-parameter configuration, BO uses two key components: a surrogate model and an acquisition function. The surrogate model aims to fit all the currently-observed points into the objective function. After obtaining the predictive distribution of the probabilistic surrogate model, the acquisition function determines the usage of different points by balancing the trade-off between exploration and exploitation. BO models balance the exploration and the exploitation processes to detect the current most likely optimal regions and avoid missing better configurations in the unexplored areas.
#### The basic procedures of BO are as follows:
1. Build a probabilistic surrogate model of the objective function.
2. Detect the optimal hyper-parameter values on the surrogate model.
3. Apply these hyper-parameter values to the real objective function to evaluate them.
4. Update the surrogate model with new results.
5. Repeat steps 2 - 4 until the maximum number of iterations is reached.

#### Common Surrogate models for BO include:
- Gaussian Process (GP) : BO-GP
- Random Forest (RF) : BO-RF
- Tree Parzen Estimator (TPE) : BO-TPE (default in `optuna`, hyper parameter optimization library.)


### Multi-fidelity optimization
Mutlifidelity optimization techniques are common approaches to solve the constraint of limited time and resources. The most common algorithm is bandit-based algorithms. **Hyperband** is a popular bandit-based optimization technique that can be considered an improved version of RS. It generate small versions of datasets and allocates same budget to each hyper-parameter combination. In each iteration of Hyperband, poorly-performing hyper-parameter configurations are eliminated to save time and resources.
#### Algorithms
- Successive Halving
- Hyperband
- BOHB ( Bayesian Optimization HyperBand )

### Metaheuristic algorithms
A set of techniques used to solve complex, large search space and non-convex optimization problems to which HPO problems belong. Among all metaheuristic methods, **genetic algorithm** (GA) and **particle swarm optimization** (PSO) are the two most prevalent metaheuristic algorithms used for HPO problems.
Genetic algorithms detect well-performing hyper-parameter combinations in each generation, and pass them to the next generation until the best-performing combination is identified.
In PSO algorithms, each particle communicates with other particles to detect and update the current global optimum in each iteration until the final optimum is detected.
Metaheuristics can efficiently explore the search space to detect optimal or near-optimal solutions.They can be used in deep learning model which include large configuration space with multiple hyper-parameters, including the activation and optimizer types, the learing rate, drop-out rate, etc.
#### Algorithms
- Genetic Algorithm
- Particle Swarm Optimization

### Mathematical Optimization and Hyper-parameter Optimization Problems
The key process of machine learning is to solve optimization problems. To build a ML model, its weight parameters are initizalied and optimized by an optimization method utnil the objective function approaches a minimum value or the accuracy approaches a maximum value.
Similarly, hyperparameter optimization method aim to optimize the architecture of ML model by detecting the optimial hyper-parameter configurations.

#### Mathematical Optimizatoin
Generally, there are two types of optimization problems based on whether they have constraints or don't have the constraints for the decision variables.
In unconstrained optimization problems, a decision variable, $x$, can take any values from the one-dimensional space of all real numbers, $R$. An unconstrained optimization problems can be denoted by
$$min_{x\in \mathbb{R}}f(x)$$
where f(x) is the object function. On the other hand, most real-life optimization problems are constrained optimization problems. Unconstrained optimization problems can be denoted by
$$
min_x f(x)
$$
$$g_i(x) \leq 0, i=1, 2, ..., m,$$
$$h_j(x) - 0, j=1, 2, ..., p,$$
$$x\in X$$
where $g_i(x), i=1,2, ..., m,$ are the inequality contraint functions; $h_j(x), j=1, 2, ..., p,$ are the quality constraint function; and X is the domain of x.
