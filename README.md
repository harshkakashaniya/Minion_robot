# Minion_robot
Reinforcement Algorithm with Deep Q nework (DQN)  
Here we are training the agent to grab yellow bananas(Reward +1) and leave the blue ones(Reward -1). 
In our case environment is considered to be solved if it can get at average of 16 points over 100 episodes.


### Output of the algorithm

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/banana.gif)

If you wish to just run the pre-trained model run the file 

[Testing program](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/Navigation_testing.ipynb)

If you want to train your own model you will refer the file.

[Training program](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/Navigation.ipynb)

## Setup environment:

1. First we have to install conda once the conda is installed we need to update the bash script.  [Install anaconda](https://docs.anaconda.com/anaconda/install/linux/)

2. Run the following commands in the terminal.
```
conda create --name drlnd python=3.6
source activate drlnd
```

3. Clone the environment repo:
```
git clone https://github.com/udacity/deep-reinforcement-learning.git
cd deep-reinforcement-learning/python
pip install .
```

4. Clone this repo :
```
git clone https://github.com/harshkakashaniya/Minion_robot.git
cd Minion_robot
```

5. Setup drlnd environment :
```
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```
6. Finally open the Jupyter noetbook :

```
jupyter notebook
```

And select the appropiate file to train or test the model.
(Eg. Banana Navigation >> Navigation.ipynb)

**Note : Do not forget to select Kernal >> Change kernal >> drlnd**

7. Edit the location of Banana linux in code cell 2 and run the notebook( Hit  **Shift + Enter**) 


## Project Report :

[Architecture and project report](https://github.com/harshkakashaniya/Minion_robot/blob/main/Report.md)

## Results :

### Our Average score vs Episodes.

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/training.png)

### Our Results of training.

![](https://github.com/harshkakashaniya/Minion_robot/blob/main/Banana_navigation/Episodes.png)
