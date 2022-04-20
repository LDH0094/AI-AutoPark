# Soft Actor Critic with Unity ML-agents

This project aims the notion of **"simple, yet powerful autonomous parking."**

The Unity Parking Enviornment provided (with ML-agents version Release 19) interacts with the Python API. Although it is stil possible to lauch a project without the python code on your end, this project applied python API so as to control our own  enviornment. 


### Why Unity Enviornment and not other?

Making an enviornment for a RL project is time-consuming and often times, exhausting. The need for spliting the work for both the enviornment (what we viewed as the frontend) and the Python code (as backend) was necessary. In order to do so, Unity ML-agents was the best option that we could implement in our project. Indeed, Unity allows smoother simulation and with its powerful features that involve complex physcis provided more realistic simulation during the dry run (demo simulation before training the agent). 


## AI AutoPark simulation results

Episode: 0 ~ 500 (about 50K frames)    |  Episode: 500 ~ 1500 (about 150K frames)
:-------------------------:|:-------------------------:
 gif here | gif here
 
When training data is not sufficiently stored, the agent seems lost and does not show any intelligence in searching for the right parking spot.
 
 Episode: 1500 ~ 20K (about 2M frames) |  Episode: 20K ~ 30K (about 3M frames)
:-------------------------:|:-------------------------:
 gif here | gif here

 When training data is sufficiently stored and as its following NN begins to train, the agent seems confident and finds the right parking spot. 
  

## Ray Perception sensor

<img src="/screenshots/Ray_perception_sensor.png" height="350"/> 
