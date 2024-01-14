---
layout: page
title: AeroLogix
description: Autonomous GPS-denied UAS for Warehouse Logistics
img: assets/img/grid/flipkart_grid.gif
importance: 3
category: Competitions
---

<div class=row>

</div>

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/_U0wjOnUI5I?si=HEvR3qTHfSC07nkG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</center>

### Background

Work undertaken as part of the Flipkart GRiD 2.0 Robotics Challenge.

### Brief

The PS involved developing an GPS-denied UAS which can autonomously identify a sequence randomly spaced sqaure hoops (1m width) and traverse smoothly through the arena while carrying a payload (2kg).

### Approach

**Primary Challenges:**
- Compact drone design with high payload capacity.
- Indoor Localization with high precision.
- Hoop Detection and Pose Estimation
- Smooth and continuous trajectory planning and execution.


Naturally, we divided the problem statement into the following 
sub-modules/ sub-problems to solve: 

- **Hardware Design:**
    - Fully custom-designed Airframe
    - Coaxial OctoCopter Airframe Layout:
        - Small Footprint
        - High Payload
        - Motor Failure Redundancy
        - Design Optimized for Payload Capacity
    - Low-cost on-board compute
    - Nominal AUW: 4.7kg (with 2kg payload)
    - Nominal Endurance: 9 mins
    - AirFrame Footprint: 640mm x 585mm x 250mm

<div class="row">
    
    <div class="col-sm-3 mt-3 mt-md-0"></div>
    
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/uas.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>

    <div class="col-sm-3 mt-3 mt-md-0"></div>
</div>

<div class="caption">
    BumbleBee UAS Rendering
</div>

- **Localization:** 
    - Need robust GPS-denied localisation in warehouse settings.
    - Adopted Intel RealSense T265's Stereo-Visual Inertial Odometry along with 2D LiDAR SLAM for robsut state-estimation and redundancy.
    - Completely on-board with 10-15Hz state update rate.

<div class="row">

    
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/vio.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>

    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/lidar.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>

</div>

<div class="caption">
    Different Modalities: Visulization
</div>


<div class="row">
    
    <div class="col-sm-3 mt-3 mt-md-0"></div>
    
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/state_estimation.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>

    <div class="col-sm-3 mt-3 mt-md-0"></div>
</div>

<div class="caption">
    State Estimation Architecture
</div>


- **Perception:** 
    - Robust gate detection with a hybrid RGBD-based hoop detection algorithm.
    - Used Intel RealSense D435 depth camera for the RGBD images (after depth-color alignment and calibration)
    - Use of Depth with RGB makes this significantly more robust and allows us to make our solution much more simpler and streamlined.
    - Significantly more performant as comapred to Deep Learning based approaches, alleviated need for expensive and heavy GPU-based compute. 
    - Achieved 30FPS on Rapberry Pi 4B (8GB)

<div class="row">

    
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/image_processing.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>

    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/cv_arch.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>


</div>

<div class="caption">
    Hoop Detection in Action; Image Processing Workflow
</div>

- **Planning and Control:** 
    - Planning: 
        - Challenges with Planning 
            - Modelling Intelligence to react to changes in environment
            - Computationally cost
            - Modelling unforeseen scenarios

        - Proposed Scheme: Finite-State Machine (FSM)
            - Models Hybrid scenarios naturally
            - Less computational overhead
            - Robust behaviour through modelling of failsafes
            - Hierarchically can combine with other planners to solve
            - And model complex missions


    - Trajectory Tracking:
    - Low-level Controls:

<div class="row">
    
    <div class="col-sm-3 mt-3 mt-md-0"></div>
    
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/controls.png" title="Custom UAS: BumbleBee" class="img-fluid rounded " %}
    </div>

    <div class="col-sm-3 mt-3 mt-md-0"></div>
</div>

<div class="caption">
    Planning & Controls Architecture
</div>

### Detailed System Design

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRVr5pEr39FXLvcvXZQbaOxYl-kNXX2zE721B3TQs0FEhsRUn-OIZPqeCYtySCa9g/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>


<div class="row">
    
    <div class="col-sm-3 mt-3 mt-md-0"></div>
    
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_explore/iitm_logo.png" title="example image" class="img-fluid rounded " %}
    </div>
    
    <div class="col-sm-1 mt-3 mt-md-0"></div>

    <div class="col-sm-3 mt-3 mt-md-0">
        {% include figure.html path="assets/img/grid/grid_logo.png" title="example image" class="img-fluid rounded" %}
    </div>

    <div class="col-sm-3 mt-3 mt-md-0"></div>
</div>



