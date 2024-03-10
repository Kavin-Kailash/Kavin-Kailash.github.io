---
layout: page
title: DRDO DGRE Visual UAS Exploration Challenge
description: Fast Autonomous Vision-based Exploration for SAR Operations using low-cost UAS platform
img: assets/img/drdo_explore/drdo_explore.gif
importance: 2
category: Competitions
giscus_comments: false
github: https://github.com/Kavin-Kailash/drdo_mav_exploration.git
skills: [Exploration Planning, Trajectory Optimization, Trajectory Tracking, Behavior Modelling, Pose Estimation, Visual Servoing, ArduPilot, Simulation, ROS, Gazebo]
---

<center>
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vQnMJqIGRcfkcU5o_2Xf-q-mP51ZzzzzkeHle76ilWJaZhbUH4wifEgrjDWtxwRpRp8qFt7Ve6u1827/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</center>


<div class="caption">
    Detailed System Design
</div>

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/6BeKwudJcE8?si=ryTAiXqFo0n9U0PS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</center>

<div class="caption">
    Simulation Runs
</div>

### Background
Work undertaken as part of the competition organized by Defence Research and Development Organization of India (DRDO) at the 9th Inter-IIT Tech Meet.


## Brief
Work involved development of a software stack enabling rapid and safe exploration of cluttered surroundings using MAVs equipped with Vision
based perception sensors for Target search and detection. Successful detection of the visual target (Aruco Marker) is followed by a precision landing routine. NOTE: No apriori information about the environment/target.

[Complete Problem Statement](https://drive.google.com/file/d/1U5QHwJdBRJ_RJP6IYqmUFxuMAOfshTvl/view?usp=drive_link)


## Approach

**Motion Planning:**
- Adopted a Hierarchical Motion Planning system augmented with Frontier Information Strucutres, for fast and safe exploration of the environments. The developed solution was adopted from [this](https://arxiv.org/abs/2010.11561) work.
- Exploration Planning Rate: 10Hz
- Local Planning Rate: 25Hz
- Planning Horizon: 5m

**Trajectory Tracking:**
- As our robotic system was a conventional multirotor platform, we exploited the differentially flat nature of the multirotor dynamics and hence decided to adopt a Differential Flatness based Geometric SE3 Controller based on this [work](https://ieeexplore.ieee.org/document/5717652)
- Controller Inputs: Desired Position, Velocity, Acceleration and Jerk
- Controller Outputs: Attitude Quaternion Setpoint, Thrust Setpoint
- Controller Rate: 75Hz

**Low-level Flight Stabilization & Control:**
- We adopted the [Ardupilot](https://github.com/ArduPilot/ardupilot) flight stack for the low level setpoint tracking and overall flight management. 
- Used [MAVROS](https://wiki.ros.org/mavros) to send desired Attitude+Thrust commands to the FCU running APM
- Customised the Ardupilot firmware's MAVLINK interface library to add thrust/attitude setpoint compatibility, in [GUIDED](https://ardupilot.org/copter/docs/ac2_guidedmode.html) mode 
- Only used Ardupilot's attitude and attitude-rate controllers

**Target Detection and Pose Estimation:** 
- This was solved quite easily using the [aruco_detect](https://wiki.ros.org/aruco_detect) ROS Package
- Set a post-detection filtering to only pass correct marker ID (ID 0) poses.
- Acheived a detection rate of 30Hz on 1280x720 resolution camera feed.

**Vision-based Precision Landing:** 
- Process the fiducial marker poses into MAVLINK [LandingTarget](https://mavlink.io/en/messages/common.html#LANDING_TARGET) format.
- Passed the poses to FCU via MAVROS [LandingTargetRaw](https://github.com/mavlink/mavros/blob/ros2/mavros_extras/src/plugins/landing_target.cpp) plugin

**High-level Unified ask Manager/Orchestrator:** 
- Developed a high-level task/process management node aka [Commander](https://github.com/Kavin-Kailash/drdo_mav_exploration/blob/master/interiit21-drdo-iitm/src/commander.py)
- Save computation power by starting nodes only when they are required and killing them when they are no longer needed.
- One common Interface to oversee and monitor entire mission health
- Records Time automatically between takeoff and landing on Target marker
- Save and reload commonly used launch arguments as world profiles for easy reruns and tuning
- Automatically detect and close hanging processes for a clean shutdown

<div class="row">
    <div class="col-sm-3 mt-3 mt-md-0"></div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_explore/sys_arch.jpg" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    System Architecture
</div>


Complete simulation runs can be found [here](https://drive.google.com/drive/folders/1FsI2ountCtP4dR7kJMuuxtqeFgvB6fCx?usp=drive_link).

---

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
        {% include figure.html path="assets/img/drdo_explore/tech_meet_logo.png" title="example image" class="img-fluid rounded " %}
    </div>
    
    <!-- <div class="col-sm-1 mt-3 mt-md-0"></div> -->

    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/drdo_explore/drdo_logo.png" title="example image" class="img-fluid rounded" %}
    </div>
</div>
