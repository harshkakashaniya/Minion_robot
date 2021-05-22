This report is about an algorithm to teach agent to pick yellow banana and avoid blue once.

Details of environment :

Observation space type: continuous
Observation space size (per agent): 37
Stacked Vector Observation: 1
Action space type: discrete
Action space size (per agent): 4

### Action space :

0 - walk forward
1 - walk backward
2 - turn left
3 - turn right

### Observation Space :

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction. 

### Reward :
A reward of +1 is provided for collecting a yellow banana, 
and a reward of -1 is provided for collecting a blue banana.

### Neural Network details :
