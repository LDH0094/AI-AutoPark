# Soft Actor Critic with Unity ML-agents

Inspired by Alpha Go, this project aims the notion of **"simple, yet powerful autonomous parking AI."**

The provided Unity Parking Environment (with ML-Agents version Release 19) interacts with the Python API. Although it is possible to launch the project without Python code, this project uses the Python API to control the environment directly.

**Instead of using the Unity library for the RL process (which includes techniques like DQN and Q-learning), I chose to write my own [Python code](https://github.com/Unity-Technologies/ml-agents/blob/release_20_docs/docs/Python-LLAPI.md) to control every detail of the environment. I based the implementation on the Soft Actor Critic [(SAC) paper](https://arxiv.org/abs/1801.01290), which I implemented in an IPython notebook [ipynb.](https://github.com/LDH0094/AI-AutoPark/blob/main/Soft_Actor_Critic/agent.ipynb)**


### Why Unity Environment and not others?

Creating an environment for a reinforcement learning (RL) project is time-consuming and often exhausting. Splitting the work between the environment (which I consider the frontend) and the Python code (the backend) was necessary. Unity ML-Agents proved to be the best option for my project, as it allows smoother simulation and, with its complex physics engine, provides a more realistic simulation during dry runs (demo simulations before training the agent).


## AI AutoPark simulation results

Episode: 0 ~ 500 (about 50K frames)    |  Episode: 500 ~ 1500 (about 150K frames)
:-------------------------:|:-------------------------:
 <img src="/screenshots/1.gif">  |  <img src="/screenshots/2.gif"> 
When the training data is insufficient, the agent appears lost and lacks intelligence in finding the correct parking spot. | As training data is stored and the neural network starts training, the agent begins to improve.

 Episode: 1500 ~ 20K (about 2M frames) |  Episode: 20K ~ 30K (about 3M frames)
:-------------------------:|:-------------------------:
 <img src="/screenshots/3.gif">  | <img src="/screenshots/4.gif"> 
The agent becomes more confident and consistently finds the right parking spot. | By this stage, the agent has learned effectively and shows significant improvement.

  

## Ray Perception Sensor

<img src="/screenshots/Ray_perception_sensor.png" height="350"/> 


To detect collisions within the environment, a ray perception sensor is attached to the agent. This sensor is powerful in manipulating the agent’s movement and steering angle (essential for this AI parking car project). As training progresses, the ray perception sensor acts like the car’s eyes, functioning similarly to Light Detection and Ranging (Lidar).

**Key Characteristics Observed During the Experiment:**

* The agent begins to consider its surroundings through the sensor.
* The agent starts using the sensor to manipulate its movement.
* The sensor enables the agent to perform complex parking maneuvers when the parking spot is near.


## Results and Analysis

<img src="/screenshots/result.png" height="350" width="400"/>

 **_Policy Loss: Lower values are better.._**

The graph shows slight oscillation. The first red arrow indicates that the agent quickly understood its environment. The second arrow demonstrates how an overtrained agent behaves in a settled environment. If training data is stored with a poor reward system, the agent may become as confused as it was during the initial episodes. However, this can be corrected by redefining the reward system.

## Get Started

**To get started with this project, you must install the following:**
```sh
pip install --upgrade pip
pip install tensorflow
# install the latest tensorflow-probability version
pip install --upgrade tensorflow-probability
python -m pip install mlagents==0.28.0
```

**To run this project:**
* Open and run [agent.ipynb](/Soft_Actor_Critic/agent.ipynb) file. The training will start automatically, and once completed, the saved parameters for each neural network will be loaded.
