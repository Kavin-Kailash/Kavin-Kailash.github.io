---
layout: page
title: TechnoYantra/Acceleration Robotics
description: Indoor Autonomy for Warehouse Logistics AMRs
img: assets/img/ty/intro.gif
importance: 2
category: Work
giscus_comments: false
github: 
skills: [AMRs, ROS, Gazebo, PCL, Motion Planning, Behaviour Trees, NavStack, C++, Python]
---

### Background
Carried out the development, deployment and testing of a ROS-based modular autonomous navigation stack for AMRs. Work undertaken as part of my Robotics internship at TechnoYantra (now Acceleration) Robotics India Pvt. Ltd. 


## Brief
The developed stack was centred around using the ROS [NavStack](https://github.com/ros-planning/navigation) components with extended modularity using [Behaviour Trees](https://github.com/BehaviorTree/BehaviorTree.CPP) and [Move-Base Flex](https://github.com/magazino/move_base_flex).

Using Behaviour Trees with MBF let me design sophisticated navigation workflows and behaviours which could not acheived using the base ROS NavStack.

## Approach

### Motion Planning
Safe Route Planner: GVD-based safe corridor planner
Global Planner: SBPL State Lattice Planner
Local PLanner: Time-Elastic Band (TEB) Local Planner

### Sensing
State Estimation and SLAM: 2x Sick 2D LiDARs
3D Perception: 2x Intel RealSense D435i cameras
 



<center>
<iframe src="https://drive.google.com/file/d/1nnXEnXYHK_8ji0tLsTP5_JDcam78PRTi/preview" width="640" height="480" allow="autoplay"></iframe>

</center>


<div class="caption">
    Deployment Trial Runs
</div>

<div class="row">
    <div class="col-sm-3 mt-3 mt-md-0"></div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ty/sim_trials.png" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Simulation Runs
</div>

---

<div class="row">
    <div class="col-sm-5 mt-3 mt-md-0"></div>
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ty/ty_logo_2.jpg" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>





