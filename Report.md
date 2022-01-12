# CartPole-v0 with DQN and Duel DQN
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
### DDQN

## The agent hyperparameters
- Discount factor for target Q: GAMMA = 0.9   
- Starting value of epsilon: INITIAL_EPSILON =  
- Final value of epsilon: FINAL_EPSILON =  
- Experience replay buffer size: REPLAY_SIZE =  
- Size of minibatch: BATCH_SIZE =  

## The model architecture and hyperparameters

## The detailed results
