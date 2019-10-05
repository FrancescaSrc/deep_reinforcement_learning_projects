[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135602-b0335606-7d12-11e8-8689-dd1cf9fa11a9.gif "Trained Agents"
[image2]: https://user-images.githubusercontent.com/10624937/42386929-76f671f0-8106-11e8-9376-f17da2ae852e.png "Kernel"

# Report for Project 1 - Deep Reinforcement Learning Nanodegree

![Trained Agents][image1]

This report contains the details of the code useded to solve the first project in Udacity's [Deep Reinforcement Learning Nanodegree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893) program.  

## Table of Contents


3. [//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation


### The algorithm

 The agent uses a policy to move in the environment and find the optimal policy to maximize its reward. The optimal policy is the result of a trial and error effort through which the agent leans by iteration. This kind of algorithm is called Q-Learning and the optimal policy is found by running the Q-function which calculates the expected reward for all possible actions and all possible states.

 The agent uses a deep neural network to approximate the Q-function. The Deep Q-Network contains three fully connected layers of 64, 64, 4 nodes. The learning rate is set to: 
 Decreasing the learning rate has given better results during training.

 The agent uses also an Experience Replay, the experience is stored in a buffer and the agent samples randomly form this buffer during the learning steps.

### The experiments and hyperparameters

 I have tried different learning rates and found out an interesting thing:
 the agent learns from previous trainings as well! Bij starting the agent with the trained weights and decreasing the decay, the training results even more effective and the training speeds up, resolving the enviornment in 38 episodes!

 The trained agent achieves a high score also in the testing part as shown in the tested code and in the video.


The algorithm uses the prioritized an replay, it stores a set of tupels of experiences in a replay buffer which the agent can sample and lean by reusing experiences from the past.

### Algorithm improvements

The algorithm solves a simple game but if it were used for a more difficult task several improvements could be added:
 - a Double DQN
 - a Dueling DQN
 - Prioritized experience Replay

### Prioritized experience Replay

The prioritized experience replay assign significance values to each stored tuples to give a priority.

### Double DQN

Q-learning is prone to overestimation of the action values because is based on the maximization steps which selects higher values without trying other possible values. Are these values trustful? The mechanism of double DQN provides a robust counterpoint, with an evaluation step which relies on another set of values. If the two mechanisms are not agreeing on the maximum, the value set is lower. These prevents propagating of false maximum values obtained by chance.

### Dueling DQN

The dueling DQN uses two streams, one estimates the state value function, the other the advantage for each action. The two branches are in the fully-connected layers. The Q-vakye is a combination of the two values.




### General information on Reinforcement learning

Reinforcement Learning is a branch of Machine Learning where an agent outputs an action and the environment returns an observation or the state of a system and a reward. The goal of an agent is to determine the best action to take to maximaze its total reward. The environment is unknown to the agent. Deep RL uses non linear function approximators to calculate the value actions on the base of the observations from the environment.
Deep learning is used to find the optimal parameters for this function approximators. Since the agent is handling raw data and the entire end-to-end pipeline, this is called pixels-to-action, the agent starts from raw data and chooses the action which maximizes its reward.
The RL agents can learn intuitive human behaviours, such as walking or knowledge gathering.


