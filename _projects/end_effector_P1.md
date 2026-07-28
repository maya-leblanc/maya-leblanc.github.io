---
layout: page
title: Adaptive Robotic End Effector for Q-Arm Warehouse Automation
description: A team-designed sub-100-gram 3D-printed gripper and a modular Python control stack that let a single-motor Q-arm scan, pick, and pack objects of varying shape — McMaster ENGINEER 1P13 cornerstone design project, Dec 2025.
img: assets/img/projects/robotic.png
importance: 4
category: robotics
related_publications: false
---

A full engineering-design-cycle project: my five-person team designed, fabricated, and programmed an adaptive robotic end effector for the Q-Arm platform — a **sub-100-gram, single-motor, 3D-printed gripper** paired with a modular **Python control stack** that lets the arm scan, pick, and pack objects of varying shape and size into a warehouse-style workflow. We took it from problem statement through constraints, concept convergence, CAD, simulation, fabrication approval, and a working physical demonstration.

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">&lt;100 g</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Total mechanism mass<br>(incl. fasteners)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">1</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Motor — single-actuator<br>gear-driven gripper</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">8</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Modular Python functions<br>(no global variables)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">5</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Objects of varying shape<br>scanned &amp; packed</div>
  </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/robotic.png" title="Robotic End Effector" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    3D-printed gear-driven end effector designed and integrated for the Q-Arm platform.
</div>

## The problem

Warehouse fulfillment runs on automation, but robotic grippers struggle with the reality of real inventory — a single end effector has to handle everything from delicate items to awkward parcels without dropping or crushing them. The brief was to design a next-generation end effector that could reliably pick, transport, and precisely place diverse objects, minimizing damage and cycle time — all while working within the hard limits of the Q-Arm teaching platform: a single low-force motor and a tightly bounded build envelope.

## Design constraints

The most instructive part of this project was engineering *inside a box* of fixed constraints — exactly the kind of real trade-off space industrial designs live in:

| Constraint | Requirement |
|---|---|
| Actuation | Single Q-Arm motor |
| Build envelope | &lt; 30 × 20 cm |
| Mass | &lt; 100 g including fasteners |
| Materials | 3D-printed PLA; all non-flat parts printed |
| Minimum feature size | ≥ 1 mm (2–4 mm features tolerance-checked) |
| Platform | Q-Arm compatible |
| Software | Modular functions, **no global variables** |

## Mechanical design: a gear-driven gripper

Each team member first sketched an independent concept; we then reviewed all five and merged the strongest elements into one design — a convergence step that's core to the engineering method. The result is a **four-gear, two-arm gripper** that behaves like a pneumatic gripper but is driven entirely by a gear train, using the gear ratio to amplify torque from the Q-Arm's single weak motor.

The clever part is the grip surface. Because PLA alone couldn't hold objects against the Q-Arm's low grip force, we engineered a **layered friction stack** — 3D-printed base, a thin adhesive layer, a thick sponge, and a fine sandpaper facing. The sponge conforms around the object like a soft suction pad while the sandpaper supplies the friction that keeps it from slipping mid-transport. CAD was modeled in **Autodesk Inventor** and validated in simulation before anything hit the print bed.

## Software: modular warehouse control

The control side was a Python program that runs a full warehouse order workflow and drives the Q-Arm, tested in **Quanser Interactive Labs**. A strict rule — no global variables — forced clean separation of concerns across the function set:

| Function | Role |
|---|---|
| `password_valid()` | Enforces password-strength rules |
| `sign_up()` | Creates a new user account |
| `authenticate()` | Verifies user credentials |
| `lookup_products()` | Matches scanned codes to the product database |
| `complete_order()` | Totals the order, prints a receipt, appends to a CSV |
| `customer_summary()` | Reads the CSV and prints a per-user order summary *(my function)* |
| `pack_products()` | Drives the Q-Arm to pick and place each product |
| `main()` | Interactive loop: authenticate → scan codes until "done" → look up → pack via Q-Arm → complete order → summary |

Driving the arm was itself a constraint problem: the Q-Arm moves only in fixed directions at an unchangeable speed, so packing each object meant solving the exact turn angles and arm-lowering distances by coordinate — largely through disciplined trial and error mapped one-to-one to each product.

## Engineering process &amp; iteration

We ran the project through the formal milestone cycle with TA design reviews at every stage, treating feedback as design input: adding grip contact points so objects wouldn't fall off, ensuring the rack cleared the back of the effector, and sequencing the code so the rotating gears wouldn't collide. The mechanism passed **fabrication approval** against explicit gates — under the 100 g mass limit, properly toleranced to the engineering drawings, and every feature at least 1 mm — and the effector went through a full rebuild to get the tolerances and gear meshing right before the final integrated demonstration.

## Strengths &amp; limitations

The gear-based approach wins on cost and serviceability: gears are the only moving parts, so manufacturing is cheap, faults are fast to locate, and the small package stays agile — attractive at warehouse scale. The honest trade-offs: large or very flat objects don't let the jaws close far enough to fully engage the friction pad, and 3D-print tolerance is a real risk — insufficient infill or over-fast printing makes the gears liable to snap, so print quality directly gates mechanical reliability.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>My contributions</strong> — this was a five-person cornerstone design project (Team Mon-39). I served as team <em>Administrator</em> and:
<ul style="margin: 0.5rem 0 0 0;">
<li>contributed to the design and full rebuild of the end-effector mechanism;</li>
<li>authored the <code>customer_summary()</code> function;</li>
<li>wrote the executive summary and technical documentation; and</li>
<li>owned project scheduling and delivered the final Gantt chart.</li>
</ul>
</div>

---

**Context:** McMaster University · ENGINEER 1P13 — Integrated Cornerstone Design Projects in Engineering · December 2025.

**Engineering skills:** mechanical design &amp; CAD (Autodesk Inventor) · design under constraint · 3D-printing / design for fabrication · gear &amp; mechanism design · Python programming · robotics integration (Q-Arm, Quanser Interactive Labs) · modular software architecture · team-based engineering design process.
