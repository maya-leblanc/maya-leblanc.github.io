---
layout: page
title: ROS2 Robot Simulation and Sensor Integration
description: Differential-drive mobile robot in ROS2 using URDF/Xacro -> RViz -> Gazebo. LiDAR sensor feedback with TF transforms and keyboard teleoperation.
#img: assets/img/projects/
importance: 6
category: robotics
related_publications: false
---

Built and simulated a differential-drive mobile robot in ROS2. Modeled robot geometry in URDF/Xacro, visualized in RViz, simulated physics in Gazebo, and integrated LiDAR sensor feedback with TF transforms and keyboard teleoperation.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/camera_mount.jpg" title="2-DOF Pan-Tilt Camera System" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/camera_mount_front.jpg" title="Front view" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: isometric SolidWorks render. Right: front view showing the U-frame yoke, tilt servo, and pan gear train.
</div>

A custom 1:2 spur gear train resolves the SG90 servo's 180° native range to the full 360° pan requirement. A 608 ball bearing supports the rotating platform, offloading radial and axial loads from the servo gearbox — directly addressing the gear failure mode of the previous mount.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/camera_mount_exploded.jpg" title="Exploded view" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Exploded view showing all printed components, gear train, bearing, and servo locations.
</div>

**Key design decisions:** 1:2 gear ratio for 360° pan, 608 bearing for load isolation, U-frame yoke for two-sided camera support, heat-set inserts at the yoke top joint, internal cable routing for clean field operation.

**Tools:** ROS2, RViz, Gazebo, URDF/xacro, LiDAR, TF.
