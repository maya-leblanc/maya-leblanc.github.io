---
layout: page
title: Dual-GPS Antenna Mast — Mars Rover
description: Solo mechanical & materials design of a dual-GPS antenna mast for McMaster's Mars Rover (URC 2026) — PLA brackets on a hollow carbon-fibre mast carrying four antennas at a 1 m baseline, validated with modal FEA. In active development.
img: assets/img/projects/dual.png
importance: 2
category: robotics
related_publications: false
---

A solo, ground-up mechanical and materials-engineering project for **McMaster's Mars Rover Team (MMRT)**, targeting the University Rover Challenge (URC) 2026. I designed a dual-GPS antenna mast, a primary and a secondary mount set **~1 metre apart** on the rover, that rigidly carries four antennas through rough desert terrain while staying under the rover's mass and height limits. As the sole member of the Communications Systems subteam, I modeled every part from scratch in SolidWorks and validated the structure with modal (natural-frequency) FEA.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.25rem 0;">
<strong>Under construction.</strong> This is an active project for the URC 2026 rover, which the team is building from scratch. The mast has been designed and analyzed but is <strong>not yet field-deployed</strong> — validation is ongoing, and this page reflects work in progress.
</div>

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">1 m</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Antenna baseline<br>separation</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">48.7 Hz</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">First-mode resonance<br>(modal FEA)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">200 mm</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Ground-plane Ø<br>(optimized of 5)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">4</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Antennas carried<br>across both mounts</div>
  </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/dual_gps.jpg" title="Primary GPS antenna mount" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/dual_gps_secondary.jpg" title="Secondary GPS antenna mount" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: primary antenna mount (GPS + LoRa + Rocket M2). Right: secondary GPS mount. Both modeled in SolidWorks and 3D-printed in PLA on a carbon-fibre mast.
</div>

## Why two GPS antennas

Placing two GPS antennas about a metre apart does two useful things. First, **spatial diversity**, if one antenna catches a reflected, degraded signal (common in rocky terrain, where signals bounce off surfaces before reaching the antenna), the other, a metre away, is likely seeing a cleaner one, so the rover keeps a reliable fix. Second, a fixed, known separation between two GPS units gives the rover a stable **heading reference**, a way to know which direction it's pointing, not just where it is. Both matter for autonomous navigation on a course with no landmarks.

## Requirements &amp; constraints

The mast was designed to the URC 2026 rules and had to satisfy several hard constraints at once:

| Parameter | Detail |
|---|---|
| Primary mount payload | GPS u-blox antenna (on a ground plane) + LoRa antenna + Rocket M2 radio |
| Secondary mount payload | GPS u-blox antenna |
| Baseline separation | ~1 m (primary ↔ secondary) |
| Ground plane | 3 mm × 200 mm-Ø metal disc (chosen from 5 tested diameters) |
| Mast | Hollow Thornel carbon-fibre rod |
| Brackets | FDM 3D-printed PLA, lightweighted |
| Height adjustment | Clamp + clevis pin, 3 selectable positions |
| Mass budget | ~5 kg |
| Height limit | Under the rover's 1 m maximum (URC rule) |

Structurally, the mount had to survive **vibration and shock over rough terrain**, hold the antennas **rigidly pointed** (small wobble can cause GPS dropouts or heading error), and fit under the 1 m height cap — all while staying within the mass budget.

## Design &amp; materials

The core decision was **splitting materials by job**. The brackets and antenna holders are **3D-printed PLA**: they're geometrically complex, carry relatively light antennas, and — crucially for a first build — PLA is cheap, fast to print, and easy to iterate on when a design changes. The load-bearing mast, which has to carry all that weight rigidly without adding mass, is a **hollow carbon-fibre rod** — carbon fibre gives an excellent stiffness-to-weight ratio, and making it hollow removes material from the center (which contributes little to stiffness) to save even more mass. In short: printed plastic for the intricate light parts, carbon fibre for the structural backbone.

*(Honest note on PLA: I chose it for prototyping speed and cost, and the test environment doesn't demand a specialized filament. PLA is the weakest material in the assembly, though — a known limitation I'm tracking through the analysis below, and a candidate to upgrade for the final competition build.)*

A few other engineered details:

- **Lightweighting.** Cut-out holes through the bottom of the main holder remove mass wherever the structure doesn't need it.
- **Adjustability.** The carbon-fibre rod has three holes at its base; a clamp and clevis pin let me set the mast to one of three heights for alignment and fine-tuning in the field, with the pin passing through both walls of the clamp for a secure, symmetric hold.
- **Ground plane.** The GPS antenna sits on a 3 mm-thick, 200 mm-diameter metal disc. A metal ground plane under a GPS antenna shapes its reception pattern and suppresses reflected (multipath) signals — too small and reception suffers, too large and you waste mass and space. I tested five diameters and **200 mm was the sweet spot.**
- **Vibration damping.** The clamp joint at the base includes a dampener at the connection to help isolate vibration at the mount rather than along the whole link.

## Analysis &amp; validation

**Modal (natural-frequency) FEA.** Every structure has frequencies it naturally "wants" to vibrate at. If the rover happens to shake the mount at one of those frequencies, the mount *amplifies* the shaking instead of absorbing it — like pushing a swing in rhythm — which could shake the GPS lock loose or fatigue-crack the PLA over time. So the goal is to keep the mount's resonances away from the vibration the rover actually produces. The analysis put the **first resonance at 48.7 Hz**, with the next modes at 58, 62, 74, and 83 Hz — well spaced, with nothing clustered in a way that would cause combined-resonance problems. The practical next step is to check that the drive motors' operating vibration doesn't land in that 48–83 Hz band; if it does, the fix is to stiffen the bracket (which pushes resonances higher) or add a rubber isolation mount.

**Bolted-joint check.** From the 3 N·m tightening torque, all four counterbore screws carry roughly **2,350 N of axial preload**. One screw stands out: **Screw-4 sees ~116 N of shear — about 5× the others.** Shear is the force that snaps a bolt sideways or tears out the plastic hole around it, and because PLA is far weaker than the metal parts (~50 MPa tensile vs. 310+ MPa for the aluminum and steel), that screw location is the assembly's predicted weak point — exactly where I'd reinforce or add a gasket first.

**What's still being validated.** The static stress and displacement results from the FEA are currently unreliable due to boundary-condition issues I'm still resolving, so I'm only trusting the modal frequencies and the locally-computed bolt loads for now. Sorting out those boundary conditions is part of the ongoing work before the build is finalized.

## Status &amp; next steps

The mast is fully designed and partially validated, but **not yet built into the competition rover or field-tested.** Remaining work: correlate the drive-motor vibration frequencies against the resonance band, add a rubber isolation gasket at the antenna-plate joint if needed, resolve the static-FEA boundary conditions, and fabricate and field-test the mast ahead of URC 2026.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>My role — solo designer.</strong> I own this project end to end as the sole member of MMRT's Communications Systems subteam: requirements, CAD, material selection, FEA, and validation, all modeled from scratch (no pre-made parts edited), with design-review feedback from a few of the team's mechanical and software leads.
</div>

---

**Context:** McMaster Mars Rover Team · University Rover Challenge (URC) 2026 · in active development.

**Engineering skills:** mechanical design · SolidWorks CAD · design for additive manufacturing (FDM/PLA) · materials selection (PLA vs. carbon fibre) · modal / natural-frequency FEA · bolted-joint &amp; preload analysis · GPS antenna integration &amp; ground-plane design · design for serviceability.
