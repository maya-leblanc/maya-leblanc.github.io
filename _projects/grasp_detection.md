---
layout: page
title: Power Grasp Detection on 3D Objects via Multi-Height Mesh Analysis
description: Grasp planning algorithm for 3D objects using multi-height mesh analysis. Referred by Dr. Gary Bone, PhD. MATLAB, computational geometry, algorithm design.
img: assets/img/projects/grasp_plan.png
importance: 3
category: robotics
related_publications: false
---

Grasp planning programming challenge referred by Dr. Gary Bone, PhD (McMaster Mechanical Engineering, Robotics Manipulation and Autonomy Lab). The project develops an algorithm for identifying viable power grasp locations on arbitrary 3D objects using multi-height mesh cross-section analysis.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/grasp_detection.jpg" title="Grasp detection algorithm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Multi-height mesh cross-section analysis identifying viable power grasp regions on a 3D object.
</div>

The algorithm slices a 3D mesh at multiple heights, analyses cross-sectional geometry at each slice, and identifies regions satisfying power grasp constraints. Implemented in MATLAB using computational geometry primitives.

**Tools:** MATLAB, computational geometry, 3D mesh processing.
