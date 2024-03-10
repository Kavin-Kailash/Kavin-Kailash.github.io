---
layout: page
title: Recruit Robotics
description: L3.5+ Flight Autonomy stack for Autonomous Aerial Logisitics transport in Urban Settings
img: assets/img/sald/demo.gif
importance: 2
category: Work
giscus_comments: false
github: 
skills: [Route Optimization, Motion Planning, Trajectory Optimization, Controls, Behaviour Trees, PCL, OpenCV, Gazebo, ROS, ArduPilot]
---

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/i_isqmy8f3U?si=WoEbYvcNISFyl2sk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</center>


<div class="caption">
    Simulated Demo
</div>

### Background
Development of a Modular and Hierarchical Large-Scale Multi-Goal Navigation Stack in Large Scale Urban settings for last-mile aerial logistics. I worked on this problem while being employed at Recruit Robotics.


## Brief
This involved a multi-stop high level route optimiser (based on VROOM), a global planner (accounting for No-Fly Zones, Buildings (from OSM data), GeoFences, 2.5D Global Occupancy map based) and an multi-objective optimisation based local Trajectory planner (Local 3D SDF Map, Kino-Dynamic Limits, Length/Time Optimality), . Further for safe landing, I incorporated a terrain-flatness based landing site evaluation metric to select secondary landing spots or terminate landing.

For trajectory tracking, I employed a differential flatness based full state geometric controller.

The entire system was orchestrated using a Behaviour Tree (BT.CPP project by Davide Faconti), for rapid adaptability of the workflow.

<div class="row">
    <div class="col-sm-2 mt-3 mt-md-0"></div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/sald/local_planner.png" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Local Planner
</div>

<div class="row">
    <div class="col-sm-2 mt-3 mt-md-0"></div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/sald/osm.jpeg" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Custom OSM Buildings costmap plugin
</div>

<div class="row">
    <div class="col-sm-2 mt-3 mt-md-0"></div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/sald/prec_land.png" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Precision Safe Lander
</div>

---

<div class="row">
    <div class="col-sm-5 mt-3 mt-md-0"></div>
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/sald/rr_logo.png" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>





