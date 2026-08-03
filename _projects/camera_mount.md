---
layout: page
title: 2-DOF Pan-Tilt Camera System — Mars Rover
description: Solo design of a servo-actuated pan-tilt camera mount for McMaster's Mars Rover (URC 2026) — a custom 1:2 spur gear train for 360° pan and a 608 bearing that fixes the previous mount's gear failure. SolidWorks, PLA FDM. In active development.
img: assets/img/projects/2dofcam.png
importance: 1
category: robotics
related_publications: false
---

Sole designer of a 2-degree-of-freedom (pan + tilt) actuated camera mount for **McMaster's Mars Rover**, competing in the University Rover Challenge (URC). Designed to be the rover's primary "eye" — giving the operator a steady, aimable view for driving and completing tasks — the system delivers **360° pan and 180° tilt**. It's a ground-up replacement for last year's mount, re-engineered around the specific failure that took the old one down.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.25rem 0;">
<strong>Under construction.</strong> The design is complete and I'm currently bench-testing the mechanism to see how it runs. It has <strong>not yet been analyzed in FEA or field-deployed</strong> — this page reflects an active, in-progress project for the URC 2026 rover.
</div>

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">360°</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Pan coverage</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">180°</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Tilt coverage</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">1:2</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Gear ratio<br>(servo 180° → 360° pan)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">608</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Ball bearing<br>(offloads gear loads)</div>
  </div>
</div>

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

## What it has to do

The mount's job is simple to state and easy to get wrong: hold a Logitech camera **steady enough that the operator can reliably drive and aim**, and cover the **field of view** the rover's tasks demand — a full 360° around the rover for finding markers and targets, and 180° of tilt to look from the ground up to the horizon. Because the camera is light, payload mass wasn't a design driver; the real challenges were the range of motion and durability under a rover's constant vibration.

| Parameter | Detail |
|---|---|
| Degrees of freedom | 2 (pan + tilt) |
| Pan range | 360° (via 1:2 gear train) |
| Tilt range | 180° |
| Actuators | 2 × TowerPro SG90 servo |
| Pan bearing | 608 ball bearing |
| Camera | Logitech webcam |
| Structure | FDM 3D-printed PLA, U-frame yoke |
| Application | Primary camera, McMaster Mars Rover (URC 2026) |

## The engineering

**The 1:2 gear train (getting 360° out of a 180° servo).** An SG90 servo only sweeps 180°, but the rover needs to see a full 360° around itself. A custom 1:2 spur-gear train solves this: it makes the camera platform rotate **twice as far as the servo turns**, so a 180° servo sweep becomes a 360° pan. That step-up isn't free, and the expected trade-offs are worth naming: doubling the output angle roughly **halves the torque** delivered to the platform and **halves the angular resolution** (each servo step moves the camera twice as far, so aiming is a bit coarser). Both are acceptable here — the camera is light, so torque isn't the constraint, and a driving view doesn't need fine positioning. These are the anticipated consequences of the ratio; confirming them (and the gear backlash) is exactly what the current bench testing is for.

**The 608 bearing (fixing the failure that killed the last mount).** Last year's mount failed at the gears — the servo's own plastic gears were forced to *both* rotate the camera and carry its weight and side loads, and that combined duty is what broke them. A **608 ball bearing** (a standard, robust skate-type bearing) now supports the rotating platform directly. Bearings are built to carry radial and axial loads while spinning freely; gears aren't. So the bearing takes the structural load, leaving the servo gears to do only what they're good at — transmitting motion. That single change directly targets the previous mount's failure mode.

**Servos — reusing a proven part.** The SG90s are hobby-grade micro servos, but they've held up across the team's previous competitions, and with a light camera and the new bearing offloading the gears, there's no need to over-build. Reusing a part with a competition track record cuts risk on a from-scratch rover.

**U-frame yoke.** The camera is cradled in a two-sided U-frame yoke rather than cantilevered off one side — supporting it from both ends keeps it stable and resists the sag and twist a single-sided mount would suffer under vibration.

## Design process &amp; status

The full assembly is modeled from scratch in SolidWorks, and I'm now in the **bench-testing phase** — running the mechanism to see how the gear train, bearing, and servos actually behave together before committing to the competition build. No FEA has been done on this mount yet; validation at this stage is hands-on test-and-iterate. It is **not yet field-deployed**, and the design will keep evolving as testing surfaces what to refine.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>My role — solo designer.</strong> I designed this mount end to end as the sole designer: requirements, the gear-train and bearing scheme, full SolidWorks CAD, and the current testing — a complete, from-scratch replacement for the team's previous camera mount on the URC 2026 rover.
</div>

---

**Key design decisions:** 1:2 gear train to reach 360° pan from a 180° servo · 608 bearing for load isolation (fixing the prior mount's gear failure) · U-frame yoke for two-sided camera support · competition-proven SG90 servos reused to reduce risk.

**Context:** McMaster Mars Rover Team · University Rover Challenge (URC) 2026 · in active development.

**Engineering skills:** mechanical design · SolidWorks CAD · gear-train design · bearing &amp; load-path engineering · failure analysis &amp; redesign · design for additive manufacturing (FDM/PLA) · servo actuation.
