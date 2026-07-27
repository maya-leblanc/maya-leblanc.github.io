---
layout: page
title: Power Grasp Detection for Arbitrary 3D Objects
description: An in-progress robotics algorithm for identifying viable power-grasp regions on arbitrary 3D objects. Referred and guided by Dr. Gary Bone (McMaster Robotics and Manufacturing Automation Lab). MATLAB, computational geometry. Active development.
img: assets/img/projects/grasp_plan.png
importance: 3
category: robotics
related_publications: false
---

An ongoing algorithm-development project in robotic manipulation: teaching a system to look at an arbitrary 3D object and work out *where* a robotic hand could grip it for a stable power grasp. The work was referred and is guided by **Dr. Gary Bone** (McMaster Mechanical Engineering, Robotics, Manipulation &amp; Autonomy Lab), and is under active development.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.25rem 0;">
<strong>Work in progress.</strong> This project is actively evolving. The page below describes the problem and general direction — the specific method and results are still being developed and are intentionally kept high-level for now.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/grasp_detection.jpg" title="Grasp detection algorithm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Identifying viable power-grasp regions on a 3D object through geometric analysis.
</div>

## The problem

For a robot to reliably pick up an object it has never encountered, it first has to solve a deceptively hard question: *where should it grip?* The answer depends entirely on the object's three-dimensional shape. A **power grasp** — where the hand wraps its palm and fingers fully around an object for maximum security and load capacity — needs geometry that the hand can actually envelop and hold without slipping. Finding those regions automatically, for arbitrary and irregular shapes, is a genuinely open challenge in robotic grasp planning, and it sits upstream of nearly every real-world manipulation task.

## Approach

The project works from an object's 3D mesh and applies **computational-geometry** techniques in **MATLAB** to reason about its shape and surface it into candidate regions where a stable power grasp is geometrically feasible. The emphasis is on handling arbitrary geometry rather than a fixed catalog of known shapes.

Because this is active, exploratory research, I'm keeping the specific method and its results under wraps while the work matures.

## Status &amp; next steps

The algorithm is in active development — I'm refining the core approach and validating its behavior across a range of object geometries. As the method stabilizes and results are confirmed, I'll expand this page with the technical detail and outcomes.

## Context

Referred and mentored by **Dr. Gary Bone**, whose Robotics and Manufacturing Automation Lab at McMaster works on robotic grasping and autonomous manipulation — situating the project within active academic research in the field.

---

**Engineering skills:** algorithm design · computational geometry · 3D mesh processing · MATLAB · robotic grasp planning.
