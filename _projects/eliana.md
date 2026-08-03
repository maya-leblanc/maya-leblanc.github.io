---
layout: page
title: Differential-Drive Mobile Robot — ROS 2 Simulation & LiDAR
description: A differential-drive mobile robot simulated in ROS 2 Jazzy and Gazebo Harmonic — parametric URDF/Xacro model, 360° LiDAR integrated through the TF transform tree, ROS–Gazebo bridging, and keyboard teleoperation.
img: assets/img/projects/gazebo.jpg
importance: 6
category: robotics
related_publications: false
---

A from-scratch simulation of a two-wheeled **differential-drive mobile robot**, built for **ROS 2 Jazzy** and **Gazebo Harmonic**. The robot is modeled parametrically in URDF/Xacro, simulated with full physics in Gazebo, and driven live through keyboard teleoperation. A 360° LiDAR is integrated through the **TF transform tree**, so its scans are correctly localized to the robot as it moves — the foundation for mapping and navigation.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/diffbot_gazebo.jpg" title="Robot and obstacles in Gazebo Harmonic" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/diffbot_rviz.jpg" title="LiDAR scan and TF tree in RViz" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the robot and obstacles in Gazebo Harmonic. Right: RViz showing the live LiDAR scan tracing the obstacles, with the TF frames attached to the robot.
</div>

The full pipeline runs from mechanical model to sensor feedback: a parametric Xacro description (chassis, drive wheels, caster, LiDAR mast, with reusable inertia macros) is spawned into a Gazebo world, actuated by the `gz-sim-diff-drive-system` plugin, and connected to ROS 2 through the `ros_gz` bridge. Velocity commands from `teleop_twist_keyboard` flow over `/cmd_vel` into the drive plugin, which resolves them into per-wheel motion and publishes odometry.

The LiDAR integration is the technical centerpiece. A 360° `gpu_lidar` sensor publishes range scans stamped to the `lidar_link` frame. Because `robot_state_publisher` and the drive plugin jointly maintain the transform chain `odom → base_footprint → base_link → lidar_link`, every scan is placed correctly in the world frame as the robot drives — exactly what a downstream mapping or navigation stack needs.

**Key elements:** parametric URDF/Xacro modeling with inertia macros, differential-drive kinematics via `gz-sim` plugins, 360° LiDAR with correct TF frame stamping, bidirectional ROS–Gazebo bridging (`/cmd_vel`, `/odom`, `/tf`, `/joint_states`, `/scan`), and real-time keyboard teleoperation.

**Next steps:** 2D occupancy mapping with SLAM Toolbox and autonomous navigation with Nav2, building directly on the existing LiDAR + TF foundation.

**Tools:** ROS 2 Jazzy · Gazebo Harmonic · URDF/Xacro · RViz2 · `ros_gz_bridge` · LiDAR · TF · Ubuntu 24.04
