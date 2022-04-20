# Soft Actor Critic with Unity ML-agents

This project aims the notion of **"simple, yet powerful autonomous parking."**

The Unity Parking Enviornment provided (with ML-agents version Release 19) interacts with the Python API. Although it is still possible to launch a project without the python code on your end, this project applied python API so as to control the enviornment. 


### Why Unity Enviornment and not other?

Making an enviornment for a RL project is time-consuming and often times, exhausting. The need for spliting the work for both the enviornment (what we viewed as the frontend) and the Python code (as backend) was necessary. In order to do so, Unity ML-agents was the best option that we could implement in our project. Indeed, Unity allows smoother simulation and with its powerful features that involve complex physcis provided more realistic simulation during the dry run (demo simulation before training the agent). 


## AI AutoPark simulation results

Episode: 0 ~ 500 (about 50K frames)    |  Episode: 500 ~ 1500 (about 150K frames)
:-------------------------:|:-------------------------:
 <img src="/screenshots/1.gif"> |  <img src="/screenshots/2.gif"> 

When training data is not sufficiently stored, the agent seems lost and does not show any intelligence in searching for the right parking spot.
 
 Episode: 1500 ~ 20K (about 2M frames) |  Episode: 20K ~ 30K (about 3M frames)
:-------------------------:|:-------------------------:
 <img src="/screenshots/3.gif">  | <img src="/screenshots/4.gif"> 

 When training data is sufficiently stored and as its following NN begins to train, the agent seems confident and finds the right parking spot. 
  

## Ray Perception sensor

<img src="/screenshots/Ray_perception_sensor.png" height="350"/> 


In order to detect collision that happens within the enviornment, ray perception sensor is attached to the agent. This sensor is powerful when manipulating the agent's movement and steering angle (in our case). As training attempts continue, you will notice that the ray perception sensor starts to act as the eye of the car that works very similar to Light Detection and Ranging (Lidar). 

**Three key charaterics were observed during the experiment and theses are:**

* The agent starts to consider its surrounding through the sensor.
* The agent begins to use the sensor to manipulate its movement.
* The sensor allowed complicated parking control when parking spot is near. 


## Results and Analysis

<img src="/screenshots/result.png" height="350" width="400"/>

 **_Policy loss. The lower the better._**

As it is clear in the graph, there is a slight oscillation. The first red arrow provides an idea that the agent was able to quickly understand its enviornment. 

Nonetheless, the sencond arrow demonstrates how extremely trained agent behave in the settled enviornment. When training data is stored with poor reward setting, the agent is again completely lost just like it behaved during the first few episodes. 

This issue can, however, be fixed with re-defining its reward system. 
## Get Started

**To get started with this project, you must install:**
```sh
pip install --upgrade pip
pip install tensorflow
# install the latest tensorflow-probality version
pip install --upgrade tensorflow-probability
python -m pip install mlagents==0.28.0
```

**To run this project:**
* Open and run [agent.ipynb](/Soft_Actor_Critic/agent.ipynb) file. The training will automatically start and when finished will load the saved parameters for each NN. 
