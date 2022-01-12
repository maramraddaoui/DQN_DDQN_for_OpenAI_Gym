# CartPole-v1 with DQN and Duel DQN
## The CartPole Environment
![This is an image](https://thumbs.gfycat.com/SmartShortClownanemonefish-size_restricted.gif)


The environment is two-dimensional and it consists of a pole which moves along 
a frictionless track. The system is controlled by applying a force of +1 or -1 
to the cart.
the goal is to prevent it from falling over.
### Observation Space:
The state space is represented by four values: 
- The cart position
- The cart velocity
- The pole angle 
- The velocity of the tip of the pole
### Actions:
The agent can take one of two different actions:
- moving left
- moving right.
### Reward:
At each step, the pole receives a reward based on the state it reached after that action:
- Reward of +1 is awarded for every timestep that the pole remains upright
### Starting State:
The pole starts upright with an initial angle between –0.05 and 0.05 radians.
### Episode Termination:
The episode ends when the pole is more than 15 degrees from vertical, or the cart moves more than 2.4 units from the center.
## Implementation

## The learning algorithms
### DQN
The QNetwork class implementation consists of a simple neural network implemented in PyTorch that has two main methods — forward and select_action. The network takes the agent’s state as an input and returns the 𝑄 values for each of the actions. 
### Duel DQN
The dueling architecture consists of two streams that represent the value and advantage functions while sharing a common convolutional feature learning module.
The two streams are combined via an aggregating layer to produce an estimate of the state-action value function Q, as shown in the following diagram:

![This is an image](https://static.packt-cdn.com/products/9781788621755/graphics/995fbe60-e65c-4bd3-823a-54792a51fbe3.png)
## The agent hyperparameters
- Discount factor for target Q: GAMMA = 0.9   
- Starting value of epsilon: INITIAL_EPSILON =  
- Final value of epsilon: FINAL_EPSILON =  
- Experience replay buffer size: REPLAY_SIZE =  
- Size of minibatch: BATCH_SIZE =  

## The model architecture and hyperparameters

## The detailed results
