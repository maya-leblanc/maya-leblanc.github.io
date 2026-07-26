---
layout: page
title: Project AURA — EEG-Controlled Robotic Prosthetic Hand
description: A full-stack, non-invasive brain-computer interface: a four-finger robotic prosthetic that translates trained mental commands into servo-driven finger motion, with fingertip haptic feedback and onboard environmental monitoring. May–June 2025.
img: assets/img/projects/Picture1.jpg
importance: 3
category: research
related_publications: false
---

A full-stack brain-computer interface built end to end: a four-finger robotic prosthetic hand controlled directly by brain signals — no surgery, no muscle input required. A non-invasive EEG headset detects trained mental commands, which are classified, streamed, thresholded, and translated into servo-driven, tendon-cable finger motion inside a 3D-printed frame — with fingertip force feedback and environmental monitoring layered on for real-world daily wear. I owned every layer of the stack: neural signal processing, Python bridge, embedded firmware, and the mechanical build.

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">4</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Individually articulated<br>fingers</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">2</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Trained mental commands<br>(LIFT / DROP)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">0</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Surgery or implants<br>(non-invasive EEG)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">4-layer</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Full stack, owned<br>end to end</div>
  </div>
</div>

## The problem

Traditional prosthetics for partial-hand amputees fall into two camps: passive cosmetic devices that restore appearance but offer no function, and myoelectric prosthetics that need sufficient residual muscle signal to operate. Neither serves amputees who have **lost all four fingers but kept the thumb** — a specific, underserved profile. Limb loss is far from rare (diabetes-related complications alone drive over 60% of lower-limb amputations in some regions), and even losing a single digit disrupts grip, manipulation, and — profoundly — psychological well-being. Project AURA targets this gap with a functional prosthetic driven by **thought rather than muscle**.

## What I built

Project AURA is a four-finger robotic prosthetic driven by a non-invasive EEG headset. A user trains two mental commands — **"LIFT"** (open/extend) and **"DROP"** (close to a fist) — which are classified, streamed to an embedded controller, and translated into servo-driven, tendon-cable finger movement housed in a lightweight 3D-printed frame. On top of the core actuation, I added two subsystems that only matter once you design for real daily use rather than a lab demo: **fingertip force sensing with vibrational haptic feedback**, so users can modulate grip without looking, and an **onboard environmental sensor** tracking socket temperature, humidity, and pressure to flag the heat buildup that causes skin irritation during extended wear. The whole system is self-contained — no external app or device is needed to operate it.

## System architecture

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/aura_architecture.jpg" title="System Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Signal path: EEG headset → Emotiv BCI classification → OSC → Python bridge → serial → Arduino → servo-driven fingers, with a parallel environmental-monitoring loop.
</div>

The pipeline, brain to motor:

1. An **Emotiv EPOC X** EEG headset reads brain signals over Bluetooth.
2. **Emotiv BCI** software classifies the trained mental commands (LIFT / DROP).
3. Classified commands stream over **OSC** (Open Sound Control) to a custom Python bridge.
4. The Python script applies an **intensity threshold (0.25)** — not a binary trigger — and sends serial commands at **115200 baud** to an Arduino Uno R3.
5. The Arduino drives **servo motors** that actuate tendon-cable-linked fingers.
6. In parallel, a **BME680** sensor continuously logs temperature, humidity, pressure, and gas resistance to an onboard 20×4 I²C LCD.

### Component specifications

| Subsystem | Implementation |
|---|---|
| Neural input | Emotiv EPOC X EEG headset — non-invasive, Bluetooth |
| Command classification | Emotiv BCI — 2 trained mental commands (LIFT / DROP) |
| Signal transport | Open Sound Control (OSC) → custom Python bridge |
| Actuation logic | Intensity thresholding (0.25) → serial @ 115200 baud → Arduino Uno R3 |
| Finger drive | Servo motors → tendon-cable linkage, 4 independent fingers |
| Frame | Lightweight 3D-printed ergonomic housing |
| Haptic feedback | Fingertip force sensors → socket-mounted vibration motors |
| Environmental sensing | BME680 (temp / humidity / pressure / gas) → 20×4 I²C LCD, 2 s refresh |
| Operation | Fully embedded — no external app required |

## Subsystem engineering

**Control.** Instead of firing on any detected command, the Python bridge gates actuation behind an intensity threshold, so weak or noisy signals don't trigger unwanted motion — a small design choice that made the difference between a twitchy demo and a controllable hand.

**Haptic feedback.** Force sensors at each fingertip read grip strength and drive vibration motors in the arm socket, closing a feedback loop that lets the user judge pressure by feel — essential for handling delicate or irregular objects without visual cues.

**Environmental monitoring.** The BME680 (with its gas-sensor heater running at 320 °C) refreshes every two seconds, surfacing internal socket conditions on the LCD. I added this specifically because extended prosthetic wear traps heat and causes irritation — a constraint invisible in a short lab test but decisive for daily use.

## Challenges &amp; engineering decisions

- **Signal reliability.** EEG quality is exquisitely sensitive to electrode contact, focus, and mental fatigue. I iterated repeatedly on sensor placement and calibration, and each small adjustment measurably improved responsiveness — reinforcing why the intensity threshold, not a raw binary trigger, was the right call.
- **Latency.** I kept the brain-to-motor path deliberately short — lightweight OSC into a minimal Python bridge into serial — to minimize the delay between intention and movement.
- **Full-stack ownership.** Rather than staying in one layer, I configured the BCI software, wrote the Python signal processing, worked the embedded firmware, and did the mechanical build — integrating four very different disciplines into one working device.
- **Human factors.** The haptic and environmental subsystems exist because I designed for a person wearing this all day, not for a benchtop demo.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>Result — a working prototype.</strong><br>
A robotic hand that opens and closes from trained mental commands alone, with fingertip haptic feedback and live environmental monitoring for wearer comfort. Brain signal to finger motion, fully self-contained.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0 text-center">
        <a href="https://github.com/maya-leblanc/project-aura" target="_blank" rel="noopener noreferrer" class="btn btn-outline-dark me-2">View on GitHub</a>
        <a href="#" target="_blank" rel="noopener noreferrer" class="btn btn-outline-dark">Watch Demo</a>
    </div>
</div>

## Reflection

The system worked best when I was completely focused and calm — distractions or mental fatigue noticeably degraded accuracy, which drove home how sensitive and personal brain-computer interfaces really are. Even a thought has to be trained, refined, and treated like a signal. Watching the hand move from intention alone made the hours of troubleshooting worth it. Next, I'd add more distinct mental commands and push response latency lower still.

---

**Engineering skills:** brain-computer interfaces (EEG) · full-stack systems integration · Python signal processing · embedded firmware (Arduino / C++) · sensor integration (BME680, force sensing) · haptic feedback design · 3D-printed mechanical design · human-factors &amp; biomedical engineering.

<div style="font-size: 0.8rem; opacity: 0.7; margin-top: 1rem;">
Project AURA was developed independently. The motor-control code (Python and Arduino) for the finger-actuation subsystem was originally written by Jordan LeBlanc and modified independently.
</div>
