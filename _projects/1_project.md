---
layout: page
title: FlexNav
description: Flexible Navigation Stack for MAVs 
img: assets/img/nav_flex/intro.gif
importance: 1
category: Self
giscus_comments: false
github: https://github.com/kavin-cmu/mav-planning
skills: [3D Mapping, Motion Planning, Trajectory Optimization, Collision Checking ,Trajectory Tracking, ArduPilot/PX4, SITL, ROS, Gazebo]
---

<center>
<iframe src="https://drive.google.com/file/d/10brcpOxPUIp0i2dsW7ujgX3aJwf3ASw0/preview" width="640" height="480" allow="autoplay"></iframe>
</center>

<div class="caption">
    3D Planning Demo
</div>

### Background
Aim of this self-learning project was to develop a flexible and modular navigation stack enabling its use for variety of applications and sensor configurations.

Salient features:
- [OMPL](https://ompl.kavrakilab.org/)-based global planners : enables choice of a wide variety of sampling-based motion planners which have been tested extensively
- Modular Map Interface: provides a modular global and local map interface, enables use of a wide variety of map representations like [OctoMap](https://octomap.github.io/), [OpenVDB](https://www.openvdb.org/), VoxelGrid etc. Local map interfaces can use SDFs for optimization based trajectory generation, presently experimenting with OctoMap's DynamicEDT3D library.
- Flexible collision-checking: adopted [FCL](https://gamma.cs.unc.edu/FCL/fcl_docs/webpage/generated/index.html) to enable support for a wide range of robot geometry/map representations and abstracts the low-level collision check queries

<div class="row">
    <div class="col-sm-3 mt-3 mt-md-0"></div>

    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/nav_flex/se2_planning.jpg" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    SE2 Planning Demo
</div>