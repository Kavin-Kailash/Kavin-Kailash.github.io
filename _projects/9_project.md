---
layout: page
title: Robotics M.Tech Thesis @ IIT Madras
description: 3D Adaptive Path-tracking control startegies for UAVs
img: assets/img/ddp/intro.gif
importance: 2
category: Academic
giscus_comments: false
github: 
skills: [Path/Trajectory Tracking, Guidance Navigation & Control, Attitude Control, Non-linear Systems]
---

<center>
<iframe src="https://drive.google.com/file/d/1Mk8EFAZ8CPfbb33GMitCFi95Ilkv7NLn/preview" width="640" height="480" allow="autoplay"></iframe>

</center>


<div class="caption">
    Final Panel Review Slides 
</div>


<center>
<iframe src="https://drive.google.com/file/d/1RroNR-KxkmUJh3aKRxif4IY6E4gH9Isy/preview" width="640" height="480" allow="autoplay"></iframe>

</center>

<div class="caption">
    Final Thesis Report
</div>

### Background
Work undertaken at IIT Madras, towards fullfilment of the M.Tech thesis for the IDDD Robotics program. 


### Brief

In recent years, the development of UAVs has increased with the low cost of sensors, airframes and electronics. As a direct consequence, UAVs have seen large scale adoption in different civilian and public safety applications like infrastructure inspection, aerial mapping, photography, search and rescue, patrol, and surveillance. Such applications necessitate the UAV to autonomously follow a predefined path at the desired speed in three-dimensional (3D) space. Most of the path-following schemes presented in the literature are limited to 2D paths and the ones developed for 3D path following are complex in their formulation and hence not easily applicable to a real-world UAV model. The goal of this study is to develop a novel guidance scheme for autonomous tracking of 3D reference paths by UAVs. It is intended for the scheme to be simple in its formulation and easily implementable for the general class of UAVs,
without compromising on the tracking performance. This work, aims to build on top of the variable look-ahead geometric (2D) path following guidance scheme [1], which was shown to perform the best among the other approaches in the same class, owing to its ability to automatically adapt the look-ahead distance on-the-go. To this end, in this work two guidance schemes are presented for 3D path-following: (i) ‘CO-AL-NLGL                                                                                                : Concurrent Orthogonal Projection based Adaptive Look-ahead Nonlinear Guidance Law’, where the 3D path tracking problem is redefined as a concurrent 2D path tracking problem; and (ii) ’3D-AL-NLGL : Three Dimensional Adaptive Look-ahead based Non-Linear Guidance Law’, where the structure of the variable look-ahead guidance algorithm [1] is generalised to enable tracking of 3D reference paths. In addition to the proposed path-following schemes, a command conversion algorithm is also presented to enable the direct application of the developed guidance schemes for quadrotor-type UAVs.


<center>
<iframe src="https://drive.google.com/file/d/17VUYYIMJeT2FV8naKiaY1IFfhTkNabU4/preview" width="640" height="480" allow="autoplay"></iframe>

</center>

<div class="caption">
    Helical Reference Path
</div>


<center>
<iframe src="https://drive.google.com/file/d/1VZ6s0h9LI1Jdhm2Mf-qph9U3Jwvb30bH/preview" width="640" height="480" allow="autoplay"></iframe>

</center>

<div class="caption">
    Leminscate Reference Path
</div>
---

<div class="row">
    <div class="col-sm-5 mt-3 mt-md-0"></div>
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/iitm_logo" title="Workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>





