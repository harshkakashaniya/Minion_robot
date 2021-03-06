This report is about an algorithm to teach agent to pick yellow banana and avoid blue once.

Details of environment :
```
Observation space type: continuous
Observation space size (per agent): 37
Stacked Vector Observation: 1
Action space type: discrete
Action space size (per agent): 4
```

### Action space :
```
0 - walk forward
1 - walk backward
2 - turn left
3 - turn right
```

### Observation Space :

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction. 

### Reward :
A reward of +1 is provided for collecting a yellow banana, 
and a reward of -1 is provided for collecting a blue banana.

### Neural Network details :
![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Neural_netowork.png)

### Agent details :
```
BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 64         # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR = 5e-4               # learning rate 
UPDATE_EVERY = 4        # how often to update the network
```
1. We have class of Ring buffer with deque of tuple [State , Action , Reward , Next state , Done ]
2. Optimizer used for back propagation is Adams.
3. E- greedy algorithm is impelemented in the choosing action function in the agent class.
4. Two networks are maintained in order to have a smooth learnings.
5. We use Tau parameter to update the network slowly so that we so not overshoot in gradient descent and function learned by the neural network is better.

### DQN algorithm.
```
number of episodes=2000, 
Maximum time step per episode =1000,
Epsilon Initial value =1.0 (Complete exploration)
Min Epsilon = 0.01 (Greedy at the end by 0.99)
Decay factor = 0.995
```

We save every training step in out reply buffer and after every 4 episodes after minimum 64 steps we take randomly 64 samples and train the network.
So if a eposide goes for 1000 time steps that means our network will update 250 times in an episode.

## Final Results :

### Result with 2 Hidden layers:
![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/3_layer_network_1.png)

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/3_layer_network_2.png)


### Single network vs Two networks.
I Started with a single network which was used for updating the weights and same network was used to compute the action. But that network did not perform to the expected level and best score over an average of 100 episodes for single network ever after 2000 episodes was approx 3 bananas. 

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/training_one_network.png)

### Adding an hidden layer in the architecture.
I added one more hidden layer of 64 neurons. But I saw some improvement. It was learning quicker as we can see in the results.

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/4_layer_network_graph.png)

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/4_layer_network.png)

**We solved the game with +13 bananas on an average of 100 episodes in 388 episodes.**


### Ideas to improve on the results.
1.We can slowly make network bigger and bigger till it starts overfitting.

2. We can also try to implement the same approach with Policy based approach rather than value based solution.

3. Also this will be a good project to try with actor critic with will decrease our variance and will improve the speed of learning.

4. If we do not have constraint of computation I will also like to try genetic algorithm and see if we can get better results I doubt it will be the case but it is a good idea to try and understand the results.
