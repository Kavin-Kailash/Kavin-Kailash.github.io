---
layout: page
title: HiveTrack
description: Target Detection and Geo-Tagging with UAV Fleet
img: assets/img/drdo_swarm/simulation.gif
importance: 2
category: Competitions
giscus_comments: false
github: https://github.com/Kavin-Kailash/AS5570-IITM-2019/tree/master/Term-Project
skills: [Multi-Agent Planning, Controls, Behavior Modelling, Object Detection, ArduPilot, ROS, Gazebo, UAV Design, CAD/CAE, Networking]
---

<iframe width="900" height="1000" src="https://docs.google.com/document/d/e/2PACX-1vSnRlhM_Qb_rN8geVWULJRCcpeKUCBCezLiTFUfUFVAYjn9Ars7VSRS7x93EC_V3UgO1DObq1-TJueK/pub?embedded=true"></iframe>

<div class="caption">
    Detailed System Design
</div>


### Background
Work undertaken as part of the competition organized by Defence Research and Development Organization of India (DRDO) at the 8th Inter-IIT Tech Meet.


## Brief
Work involved development of a Intelligent UAV Swarm system to visually detect and geo-locate a target (with known appearance) in lowest possible time. 


## Approach

**Hardware Design:**
Multirotor propulsive drive optimisation followed by fabrication and assembly of the airframe succeeded by tuning and testing of the flight performance. The combination of the fine-tuned parameters and the optimised drive will result in a better flight performance. 

<div class="row">
    <!-- <div class="col-sm-3 mt-3 mt-md-0"></div> -->
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_swarm/quad1.JPG" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_swarm/quad2.JPG" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    The developed UAV Fleet
</div>

**Exploration Planning:** 
- The exploration (path planning)  algorithm required by the fleet to coordinate and search for the predefined target using available resources and information efficiently, minimizing the time required.
- The exploration algorithm we have decided to implement is based upon Centroidal Voronoi Tessellations and is referenced from the following [paper](https://ieeexplore.ieee.org/document/5509434) . This  is a probabilistic approach in which we assume an initial uncertainty distribution about the environment (e.g a uniform distribution if the object is equally likely to be present anywhere). The uncertainty is then reduced by exploring the environment and collecting information about it using sensors (eg. in our case RGB Cameras).
- The agents are deployed in an optimal way so as to maximize the one step uncertainty reduction i.e move in an optimal way to maximize the probability of finding the target . Preliminary simulations were carried out in MATLAB and the algorithm was verified. The final implementation for the actual fleet is still in progress.
- **Salient Features**:
    - The algorithm is Optimal i.e The various UAVs deploy themselves in a manner to find targets in the fastest possible time
    - The aforementioned algorithm is dynamic and hence is adaptive to unforeseen circumstances (a UAV failing in between)  and doesn't lose out on it’s optimality
    - This Algorithm is readily scalable with respect to hardware and software requirements. The drones only require information from its neighbours to negotiate and calculate its next action

- Detailed information about the algorithm can be found [here](https://drive.google.com/file/d/1Rk1PcLfr1eyVU8um0mJ7w9oZFGf3q5nZ/view?usp=drive_link) (AS5570: Autonomous Vehicle Guidance Term Project Presentation @ IIT Madras).



**Controls and Navigation:**
- As our robotic system was a conventional multirotor platform, we exploited the differentially flat nature of the multirotor dynamics and hence decided to adopt a Differential Flatness based Geometric SE3 Controller based on this [work](https://ieeexplore.ieee.org/document/5717652)
- Controller Inputs: Desired Position, Velocity, Acceleration and Jerk
- Controller Outputs: Attitude Quaternion Setpoint, Thrust Setpoint
- Controller Rate: 75Hz

**Low-level Flight Stabilization & Control:**
- We adopted the [Ardupilot](https://github.com/ArduPilot/ardupilot) flight stack for the low level setpoint tracking and overall flight management. 
- Used [MAVROS](https://wiki.ros.org/mavros) to send desired Attitude+Thrust commands to the FCU running APM
- Customised the Ardupilot firmware's MAVLINK interface library to add thrust/attitude setpoint compatibility, in [GUIDED](https://ardupilot.org/copter/docs/ac2_guidedmode.html) mode 
- Only used Ardupilot's attitude and attitude-rate controllers

**Computer Vision:** 
- This was solved quite easily using classical CV techniques availablke in OpenCV.
- Used a highly accurate LiDAR altimeter, EKF pose estimate of the UAS along with camera parameters to geo-reference the detected target on a satellite map. 
- Acheived a detection rate of 20Hz on 1280x720 resolution camera feed.

**Communications:** 
- Fleet-GCS communications were routed through XBee Pro S3B radios.
- Mission Computer to FCU comms over serial via MAVROS.


<div class="row">
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_explore/iitm_logo.png" title="example image" class="img-fluid rounded " %}
    </div>
    
    <!-- <div class="col-sm-1 mt-3 mt-md-0"></div> -->

    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/cfi_logo.png" title="example image" class="img-fluid rounded " %}
    </div>

    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/aero_club_logo.png" title="example image" class="img-fluid rounded " %}
    </div>

    <!-- <div class="col-sm-1 mt-3 mt-md-0"></div> -->
    
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_swarm/roorkee_techmeet.jpg" title="example image" class="img-fluid rounded " %}
    </div>
    
    <!-- <div class="col-sm-1 mt-3 mt-md-0"></div> -->

    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_explore/drdo_logo.png" title="example image" class="img-fluid rounded" %}
    </div>
</div>