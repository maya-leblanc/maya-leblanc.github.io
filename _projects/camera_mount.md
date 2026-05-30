---
layout: page
title: 2-DOF Pan-Tilt Camera System
description: Servo-actuated pan-tilt camera mount for URC Mars Rover. Custom 1:2 spur gear train, 608 ball bearing, SolidWorks, PLA FDM. 360° pan, 180° tilt.
img: assets/img/projects/camera_mount.jpg
importance: 1
category: robotics
related_publications: false
---

Sole designer of a 2-DOF actuated camera mount for McMaster's Mars Rover competing in the University Rover Challenge (URC). The system provides full 360° pan and 180° tilt coverage, functioning as the rover's primary eye during competition tasks.

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

**Tools:** SolidWorks, FDM 3D printing (PLA), TowerPro SG90 servo ×2, 608 ball bearing.
