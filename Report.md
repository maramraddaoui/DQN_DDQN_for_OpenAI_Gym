# MountainCar-v0 with DQN and DDQN
## The Mountain Car Environment
![This is an image](https://gym.openai.com/videos/2019-10-21--mqt8Qj1mwo/MountainCar-v0/original.mp4)


The environment is two-dimensional and it consists of a car between two hills. 
The goal of the car is to reach a flag at the top of the hill on the right. 
The hills are too steep for the car to scale just by moving in the same direction, 
it has to go back and fourth to build up enough momentum to drive up.
### Observation Space:
The are two variables that determine the current state of the environment.

- The car position on the track, from -1.2 to 0.6
- The car velocity, from -0.07 to 0.07. Negative for left, and positive for right.
### Actions:
The car can take one of three different actions:

- Accelerate to the left
- Don't accelerate
- Accelerate to the right.
### Reward:
At each step, the car receives a reward based on the state it reached after that action:

- Reward of 0 is awarded if the agent reached the flag (position = 0.5) on top of the mountain.
- Reward of -1 is awarded if the position of the agent is less than 0.5.
### Starting State:
The car starts between the two mountains, in a random position between -0.6 and -0.4, with velocity equal to 0.

### Episode Termination:
The episode ends when the car reaches the flag (position > 0.5). The episode may also terminate when it reaches the maximum number of steps (The original value is 200. Here I used 1000 for training).

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
