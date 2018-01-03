# Note: "Deep Reinforcement Learning: An Overview"



## Introduction

This is a note of [Deep Reinforcement Learning: An Overview, Yuxi Li](paper.pdf).

This note only lists the most important concepts in this paper. Most of the idea may not be eliborated. Only key words are mentioned in the note.

To understand more about the details of reinforcement learning, please scrutinize the paper.

Note that the version of the paper this note takes on may not be the latest. To access the latest version of paper, please refer to [here](https://arxiv.org/pdf/1701.07274.pdf).



## Machine Learning

### Category

* Supervised learning
  * Classification 
  * Regression
* Unsupervised learning: representation learning
  * Clustering 
  * Density estimation
* Reinforcement learning

### Elements

* Dataset
  * Non-overlapping training, validation and testing subsets
* Cost/Loss function
  * Category
    * Training error measures the error on the training data
    * Generalization error, or test error, measures the error on new input data
  * Measurement
    The following measurements are equivalent.
    * Maximum likelihood estimation (MLE)
	* Minimize KL divergence
	* Minimize the cross-entropy
	* negative log-likelihodd (NLL)
* Optimization procedure
  * Gradient descent 
  * Stochastic gradient descent
* Model

## Deep Learning

### Algorithms

* Linear regression
* Logistic regression
* Support vector machine (SVM)
* Decision tree
* Boosting

### Elements

* Input layer
* Output layer
* Hidden layers

### Activation Function

* Logistic
* tanh
* Rectified linear unit (ReLU)

### Networks

* Multilayer perceptron (MLP)
* Convolutional neural network (CNN)
* Recurrent neural network (RNN)
  * Long short term memory network (LSTM)
  * Gated recurrent unit (GRU)

### Others

 * Gradient backpropagation: used for training all deep neural networks
 * Dropout
 * Batch normalization: normalize each training mini-batch to accelerate training by reducing internal coveriate shift



## Reinforcement Learning

### Fundamental Elements

 * State: ![state](pic/01.gif)
 
 * Policy: ![policy](pic/02.gif)
 
 * Reward: 
 
   ![discounted reward](pic/03.gif)

### Value Function

 The following decomposition uses [Bellman equation](https://en.wikipedia.org/wiki/Bellman_equation).

 * State value
 
   ![state value](pic/04.gif)
   
 * Optimal state value: 
 
   ![optimal state value](pic/05.gif)
   
   ![optimal state value](pic/06.gif)
 
 * Action value
 
   ![action value](pic/07.gif)
   
 * Optimal action value
 
   ![optimal action value](pic/08.gif)
   
### Temporal Difference (TD) Learning

 * Markov Decision Process (MDP): satisfy Markov property, i.e., the future depends only on the current state and action, but not on the past  
 
 * If RL problem satisfies the Markov property, it is define by the 5-tuple ![5-tuple](pic/16.gif).
 
 * TD learning is usually refer to the learning methods for value function evaluation
 
 * Update rule
 
   ![value update rule](pic/09.gif)
   
 * TD error
 
   ![TD error](pic/10.gif)
 
 * Some tabular algorithms
 
   ![tabular TD algorithms](pic/11.png)
 
 * Algorithm with function approximation
 
   ![algorithm with function approximation](pic/12.png)
 
 * **It is still unclear what is the root cause for instability. There are still many open problems in off-policy learning.**

### Policy Optimization

 * Advantage: ![advantage](pic/13.gif)
 
   Here the value function V(s) is the baseline.

 * REINFORCE: an policy-based algorithm.
 
   ![REINFORCE](pic/14.png)
 
 * Actor-Critic: the critic updates action-value function parameters, and the actor updates policy parameters, in the direction suggested by the critic.
 
   ![Actor-Critic](pic/15.png)
 
 * **The distinct difference between a "shallow" RL and a deep RL is what function approximator is used.**

### Reinforcement Learning Parlance

#### Problems

 * Prediction problem (policy evaluation): compute the state or action value function for a policy
 * Control problem: find the optimal policy
 * Planning problem: construct a value function or a policy with a model
 
#### Policy

 * On-policy: evaluate or improve the behavioural policy (same-policy)
 * Off-policy: learn an optimal value function or policy, maybe following an unrelated behavioural policy (different-policy)

#### Others

 * Exploration-exploitation dilemma: The agent needs to exploit the currently best action, yet it has to explore the environment to find better actions.
 * Model-free: The agent learn with trail-and-error from experience explicitly. The model is not known or learned from experience.
 * Online mode: Models are trained on data acquired in sequence
 * Offline mode (batch mode): Models are trained on the entire data set.
 * Bootstrapping: an estimate of sate or action value is updated from subsequent estimates.





