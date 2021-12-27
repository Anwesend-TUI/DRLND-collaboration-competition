# DRND-deep-reinforcement-learning Project 3 Collaboration and Competition
This Repository includes my solution to the Project Collaboration and Competition for Udacity's Deep Reinforcement Learning Nanodegree.
The following describes the project and how to set up the workspace. The results are described in more detail in `Report.md`.

# Environment and Statespace
The Projects consists of solving Unitys Tennis Environment which can be <b>downloaded</b>
[here for Windows 64bit](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
[here for Windows 32bit](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip),
[here for Linux](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip), 
and [here for Mac OS](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip).  
The Windows 64 Version is also included in this Repository.  

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

Alternatively both environments can be downloaded from the links at [this Udacity Website](https://classroom.udacity.com/nanodegrees/nd893/parts/abb587d8-60cc-4d3f-a628-8f0af120c94a/modules/d08bc8d7-fdfb-42a1-9fe4-62f5d8dcfff2/lessons/5da2debd-eae0-4a70-b21f-be1603870c27/concepts/dc754a0c-d5e1-4a04-98dc-b16bd1a93371).   

## Setting up the environment
### For Udacity workspace: 
Follow the rules of https://github.com/kitu2007/drlnd-deep-reinforcement-learning. 
The following small adjustments can be made in the process.

1. As workspace is on a Ubuntu system (or VM)
conda create --name drlnd python=3.6
source activate drlnd

2. classic control and box2d need not to be installed

3. If it was not done before: 
git clone https://github.com/udacity/deep-reinforcement-learning.git
Then, or if the repository was already cloned: 
cd deep-reinforcement-learning/python
pip install .

4. Create the Jupiter Kernel 
python -m ipykernel install --user --name drlnd --display-name "drlnd"


Full script:  
```conda create --name drlnd python=3.6  
source activate drlnd  
cd deep-reinforcement-learning/python  
pip install .  
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```

### For Windows: 
1. Install Anaconda Package Manager 

2. Clone via git (see above) or download from the [same Github Repository](https://github.com/udacity/deep-reinforcement-learning.git)

3. Install the downloaded packages
cd deep-reinforcement-learning/python
pip install .

4. Create the Jupiter Kernel 
python -m ipykernel install --user --name drlnd --display-name "drlnd"

Script in short:  
```conda create --name drlnd python=3.6  
conda activate drlnd  
cd deep-reinforcement-learning/python  
pip install .  
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```

## State and action space
The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

State and action space look like this:  
Number of agents: 2  
Size of each action: 2  
There are 2 agents. Each observes a state with length: 24  
The state for the first agent looks like:  
[ 0.          0.          0.          0.          0.          0.
0.          0.          0.          0.          0.          0. 
1.          1.            0.          0.          0.          0.         -6.65278625 -1.5 
2.          2.             -0.          0.          6.83172083  6.         -0.          0.        ]  

## The environment is considered solvend 
The task is episodic, and in order to solve the environment, the agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). 
After each episode,the rewards that each agent receives are added up to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores. This yields a single score for each episode.

The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

## How to run the code
After setting up the jupyter kernel just execute the `Tennis.ipynb` file. 

