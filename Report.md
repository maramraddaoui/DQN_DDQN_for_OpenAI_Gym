# MountainCar-v0 with DQN and DDQN
## The Mountain Car Environment
![This is an image](https://cdn-images-1.medium.com/max/800/1*nbCSvWmyS_BUDz_WAJyKUw.gif)
The environment is two-dimensional and it consists of a car between two hills. 
The goal of the car is to reach a flag at the top of the hill on the right. 
The hills are too steep for the car to scale just by moving in the same direction, 
it has to go back and fourth to build up enough momentum to drive up.
## Observation Space:
The are two variables that determine the current state of the environment.

- The car position on the track, from -1.2 to 0.6
- The car velocity, from -0.07 to 0.07. Negative for left, and positive for right.
