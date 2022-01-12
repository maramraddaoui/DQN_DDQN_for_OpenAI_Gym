# CartPole-v1 with DQN and Duel DQN
## The CartPole Environment
![This is an image](https://thumbs.gfycat.com/WelllitLawfulCero-size_restricted.gif?fbclid=IwAR1XY0ZgmXoXMUHw2psYapNg4Hu274Hhs0B3X9lc8ONNmcgUn0aFOFSwCMY)


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

- Step-1: Initialize game state and get initial observations.
- Step-2: Input the observation (obs) to Q-network and get Q-value corresponding to each action. Store the maximum of the q-value in action_index.
- Step-3: With a probability, epsilon selects random action otherwise select action corresponding to max q-value. 
- Step-4: Execute the selected action in the game state and collect the generated rewardand next state observation(next_state).
- Step-5: Pass these next state observation through Q-network and store the maximum of these Q-values. If the discount factor is Gamma then the ground truth can be calculated   as : y = batch_reward + (1 - batch_done) * GAMMA * torch.max(targetQ_next, dim=1, keepdim=True)[0]
- Step-6: Take the predicted return of current state and Y as the actual return. Calculate loss and perform an optimization step.
- Step-7: Set state = next_state.
- Step-8: Repeat Step-2 to Step-7 for n episodes.

## The learning algorithms
### DQN
A DQN is a Q-value function approximator. At each time step, we pass the current environment observations as input. The output is the Q-value corresponding to each possible action.

The QNetwork class implementation consists of a simple neural network implemented in PyTorch that has two main methods — forward and select_action. The network takes the agent’s state as an input and returns the 𝑄 values for each of the actions. 

We’ll be using experience replay memory for training our DQN. It stores the transitions that the agent observes, allowing us to reuse this data later. By sampling from it randomly, the transitions that build up a batch are decorrelated. It has been shown that this greatly stabilizes and improves the DQN training procedure.


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

## Experiment results
### DQN
Environment solved in 417 episodes with	Average Score: 197.91

![This is an image](https://github.com/maramraddaoui/DQN_DDQN_for_OpenAI_Gym/blob/main/Duel%20DQN/duel.PNG?raw=true)
### Duel DQN
Environment solved in 193 episodes with	Average Score: 195.22

![This is an image](https://static.packt-cdn.com/products/9781788621755/graphics/995fbe60-e65c-4bd3-823a-54792a51fbe3.png)
