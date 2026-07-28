---
layout: page
title: Nitrous Oxide Reduction in an Industrial Wet Scrubber Using NosZ Reductase
description: Engineered and simulated an industrial wet scrubber that uses the NosZ enzyme from P. denitrificans to convert nitrous oxide — a greenhouse gas 300× more potent than CO₂ — into inert N₂ and water. Silver at BASEF 2023, Silver Merit at CWSF 2023, Ingenious+ 2025.
img: assets/img/projects/nitrous.png
importance: 2
category: research
related_publications: false
---

A biochemical- and process-engineering design project: I translated a graduate-level enzymatic mechanism into a working reactor design, an industrial wet scrubber that channels waste nitrous oxide through a bacterially-derived enzyme (NosZ reductase from *Paracoccus denitrificans*) to convert it into inert nitrogen gas and water. Because the chemical reagents were prohibitively expensive to run physically, I engineered the full apparatus and validated its operation as a 3D process simulation and animation in Autodesk 3ds Max, a digital prototype ready for lab-scale fabrication.

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">300×</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">N₂O warming potency<br>vs. CO₂</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">N₂ + H₂O</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Inert products of<br>the reaction</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">1–15 s</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Tunable gas<br>retention time</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">1.35 V</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Enzymatic reduction<br>potential engineered for</div>
  </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/nitrous.png" title="Wet scrubber simulation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    3D simulation of the industrial wet scrubber, modelling N₂O reduction through the biological NosZ pathway.
</div>

## The problem

Nitrous oxide (N₂O) is the forgotten greenhouse gas: molecule for molecule it is **roughly 300× more potent than CO₂**, it is the single greatest human-driven threat to the ozone layer, and it pours out of fertilizer use and industrial processes like nitric- and adipic-acid production. Yet there is **no major global initiative to reduce it**, and, critically, nature has exactly **one** known way to destroy it: an enzyme called nitrous oxide reductase (NosZ). Because N₂O has a comparatively short atmospheric lifetime, cutting it delivers climate benefit fast.

## Engineering objective

Design an industrial gas-treatment system, a wet scrubber, that harnesses NosZ (produced by *P. denitrificans*) to catalytically convert an N₂O waste stream into harmless N₂ and water, and prove out its geometry, flow behavior, and operating sequence in simulation ahead of a physical build.

## The science, engineered into a reactor

NosZ catalyzes a two-electron reduction:

**N₂O + 2H⁺ + 2e⁻ → N₂ + H₂O**

The enzyme lowers the reaction's activation energy and, like all enzymes, regenerates unchanged after each catalytic cycle — so a fixed charge of biocatalyst can process gas continuously. The electrons that drive the reaction ride the bacterium's electron-transport chain (via the cytochrome *bc₁* complex and periplasmic carriers). The engineering challenge was to recreate the conditions this delicate enzymatic machinery needs — anaerobic environment, pH 7, and a continuous **+1.35 V** reduction potential — inside a controllable industrial apparatus.

## Design &amp; build: the wet scrubber apparatus

I designed a custom scrubber around five coupled requirements, each with an explicit engineering solution:

- **Retention (dwell) time.** With no prior literature to specify how long N₂O must contact the solution, I made the reactor *adjustable*. The chemical chamber telescopes from **60 cm to 180 cm in 10 cm increments**, giving a tunable **1–15 second** retention window across the expected gas flow range.
- **No-bypass geometry.** Because the gas enters under pressure, it could shortcut past the liquid. I kept the chamber long and set the liquid level in the inlet tower and outlet above the chamber top, eliminating any gas gap where N₂O could bypass the enzyme.
- **Anaerobic purge.** NosZ reacts with oxygen, so the rig purges with inert **helium** first, monitored to 100% on an outlet meter — letting me load reagents and control exactly when the reaction starts.
- **Biocatalyst concentration.** With no precedent for bacteria-to-buffer ratio at this scale, concentration is built in as a tunable experimental variable.
- **Activation energy.** A **6 V DC** battery and electrodes supply the enzyme's required +1.35 V reduction potential continuously, 6 V chosen deliberately to energize each catalytic cycle without damaging the enzyme, with a metal lining forming the chamber floor to complete the circuit.

### Design specifications

| Parameter | Design value |
|---|---|
| Reaction | N₂O + 2H⁺ + 2e⁻ → N₂ + H₂O (NosZ-catalyzed) |
| Biocatalyst | NosZ reductase from *P. denitrificans* |
| Buffer | pH 7 phosphate |
| Activation energy | +1.35 V reduction potential (6 V DC + electrodes) |
| Chamber cross-section | 6.3 cm × 6.3 cm |
| Chamber length | Adjustable 60–180 cm (10 cm steps) |
| Retention-time window | 1–15 s (tuned via length + flow) |
| Design gas flow range | 472 – 2,360 cm³/s (throttled → fully open) |
| Purge gas | Helium (inert, anaerobic prep) |
| Wetted material | PTFE (chemical-resistant) |
| Controlled output | N₂O concentration at outlet (target: zero discharge) |

The **dependent variable** is N₂O concentration leaving the scrubber, the goal being *none*. The **independent variables** are chamber length, gas flow rate (together setting retention time), and biocatalyst concentration; outlet N₂O, N₂, helium, flow, and applied voltage are all instrumented.

## Operating sequence

1. **Purge** the apparatus with helium until the outlet reads 100% — air (and its oxygen) fully displaced.
2. **Charge** the chamber with the NosZ/*P. denitrificans* buffer solution, venting displaced helium so the rig never over-pressurizes, and confirm the liquid sits above the chamber top.
3. **Admit N₂O** under slight pressure with the 6 V activation energy live; gas is forced through the enzyme solution rather than around it.
4. **Catalytic cycle**; N₂O binds the enzyme's active site, converts to N₂ + H₂O, and releases; the enzyme resets for the next molecule.
5. **Monitor &amp; tune**; the outlet N₂O meter drives adjustment: if any N₂O escapes, lengthen the chamber to add dwell time until only nitrogen discharges.
6. **Safe shutdown** — drain spent solution to a Tedlar bag, vent, and clean.

## Simulation &amp; validation

With physical reagents out of budget, I built the entire apparatus as a 3D model and animated the full process, helium purge, enzyme loading, N₂O introduction, the molecular-level catalytic cycle, and effluent discharge, in Autodesk 3ds Max. The model resolved the system's size, configuration, and component orientation and demonstrated that the gas flow, chemistry, and control logic behave as intended, giving design confidence for a lab-scale build. [View the process animation.](https://youtu.be/SwZqGICSLOo)

## Conclusions &amp; future steps

The design phase is complete and supports the hypothesis that a NosZ-based filter can reduce industrial N₂O emissions. The validated digital prototype is ready for the next stage: securing government or private funding to fabricate and run the lab-scale scrubber, then advancing to a small-scale real-world unit drawing waste gas from an industrial facility, and ultimately a full-scale deployment.

---

**Recognition:**

- BASEF 2023 — Canada-Wide Science Fair Trip Award, Silver Merit Award, Association for Iron and Steel Technology Northern Chapter Award, ArcelorMittal Dofasco Environment Award, Association for Iron and Steel Technology Northern Chapter Award, Hamilton Chamber of Commerce Innovation Award — First Place, 
- CWSF 2023 — Bronze Merit Award
- Ingenious+ 2025 recognition

**Engineering skills:** process &amp; reactor design · 3D modeling &amp; simulation (Autodesk 3ds Max) · gas-treatment/scrubber systems · biochemical &amp; enzyme engineering · design-of-experiments · instrumentation &amp; controls · systems integration.
