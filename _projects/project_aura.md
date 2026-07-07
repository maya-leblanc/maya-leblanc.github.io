---
layout: page
title: Project AURA
description: Independent research at the intersection of computer engineering, neuroscience, and biomedical engineering. May 2025 – June 2025.
img: assets/img/projects/Picture1.jpg
importance: 3
category: research
related_publications: false
---

Independent research project conducted through Aletheia at the intersection of computer engineering, neuroscience, and biomedical engineering. May–June 2025.
---

### The Problem

Traditional prosthetics for partial-hand amputees fall into two categories: passive cosmetic devices, which restore appearance but offer no active function, or myoelectric prosthetics, which require sufficient residual muscle signal to operate. Neither serves amputees who have lost all four fingers but retain the thumb, a specific, underserved population. Project AURA explores a functional alternative: a prosthetic hand controlled directly by brain signals rather than muscle activity.

### What I Built

Project AURA is a four-finger robotic prosthetic driven by a non-invasive EEG headset. A user trains two mental commands, "LIFT" and "DROP", which are classified, streamed to an embedded controller, and translated into servo-driven, tendon-cable finger movement. The system also includes fingertip force sensing with vibrational haptic feedback, and an onboard environmental sensor that monitors internal socket temperature and humidity to flag conditions that cause discomfort during extended wear.

### System Architecture

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/aura_architecture.jpg" title="System Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Signal path: EEG headset → Emotiv BCI classification → OSC → Python bridge → Serial → Arduino → servo-driven fingers, with a parallel environmental monitoring loop.
</div>

The pipeline works as follows:

1. An Emotiv EPOC X EEG headset reads brain signals over Bluetooth.
2. Emotiv BCI software classifies trained mental commands ("LIFT" / "DROP").
3. Classified commands are streamed over OSC to a custom Python bridge script.
4. The Python script applies an intensity threshold and sends serial commands to an Arduino Uno.
5. The Arduino drives servo motors that actuate tendon-cable-linked prosthetic fingers.
6. A BME680 sensor continuously monitors internal/ambient temperature, humidity, and pressure, displayed on an onboard LCD.

### Challenges & Decisions

- **Signal reliability:** EEG signal quality is highly sensitive to electrode contact, focus, and mental fatigue. I iterated on sensor placement and calibration, and built in intensity thresholding rather than binary triggers to reduce false actuation.
- **Latency:** I chose OSC over UDP with a lightweight Python bridge to keep the path from brain signal to motor actuation as short as possible.
- **Full-stack:** I owned the entire pipeline: BCI software configuration, Python signal processing, C++ firmware, and the mechanical build; rather than working in a single layer of the stack.
- **Human factors:** I added environmental sensing specifically because extended prosthetic wear causes heat buildup and skin irritation, a constraint that only becomes apparent when designing for daily use rather than a lab demo.

### Result

A working prototype that opens and closes a robotic hand from trained mental commands alone, with environmental monitoring for wearer comfort. Full technical documentation, safety information, and source code are available on GitHub.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0 text-center">
        <a href="https://github.com/yourusername/project-aura" target="_blank" rel="noopener noreferrer" class="btn btn-outline-dark me-2">View on GitHub</a>
        <a href="#" target="_blank" rel="noopener noreferrer" class="btn btn-outline-dark">Watch Demo</a>
    </div>
</div>

### Reflection

The system worked best when I was completely focused and calm, distractions or mental fatigue noticeably degraded response accuracy, which demonstrated how sensitive and personal brain-computer interfaces really are. Looking ahead, I would like to add more distinct mental commands and reduce response latency further.

---

*Project AURA was developed independently and referenced at the Bay Area Science and Engineering Fair (BASEF), 2023. Motor control code (Python and Arduino) for the finger actuation subsystem was written by Jordan LeBlanc.*
