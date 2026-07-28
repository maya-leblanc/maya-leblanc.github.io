---
layout: page
title: Household Fabric Aerosol Filtration & Improved COVID-19 Mask Design
description: Designed and built a dual-sensor aerosol test rig, screened 30 household fabrics, and developed a 3-layer mask stack reaching 99.4% filtration efficiency, approaching N-95 performance. BASEF 2021.
img: assets/img/projects/grade8.png
importance: 5
category: research
related_publications: false
---

An end-to-end materials and test-engineering project: I designed and fabricated a custom aerosol filtration test apparatus, screened 30 household fabrics against a challenge aerosol, and developed an optimized multi-layer fabric stack that reached **99.4% total filtration efficiency** and **98.9% capture of sub-micron (PM1) particles**, closing most of the gap to a medical N-95 (99.998%).

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">99.4%</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Total filtration efficiency<br>(best 3-layer stack)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">98.9%</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Sub-micron (PM1)<br>capture efficiency</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">30</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Fabrics &amp;<br>configurations tested</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">3-layer</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Engineered<br>final design</div>
  </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/grade8.png" title="COVID mask filtration research" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Custom-built aerosol filtration test apparatus used to evaluate household fabrics.
</div>

## The problem

Early in the COVID-19 pandemic, before vaccines were widely available, masks were the primary line of defense, yet medical-grade N-95 respirators were scarce and unaffordable for much of the public. I set out to answer a concrete engineering question: **can common household fabrics, combined intelligently, deliver filtration performance approaching a medical mask?**

## Engineering objective

Build a repeatable method to measure the aerosol-filtration efficiency of household fabrics, identify the best-performing materials, and engineer a layered configuration that maximizes particle capture, then benchmark it against an N-95 reference.

## Design &amp; build: a custom aerosol test rig

No off-the-shelf apparatus was available, so I designed and fabricated one. The rig drives a controlled challenge aerosol through a clamped fabric sample while two aerosol monitors measure particle concentration **simultaneously upstream and downstream**, enabling direct, real-time efficiency measurement.

| Parameter | Specification |
|---|---|
| Instrumentation | 2 × TSI DustTrak™ DRX Aerosol Monitor (Model 8533) |
| Measurement channels | PM1, PM2.5, Respirable (PM4), PM10, Total mass |
| Challenge aerosol | Talcum powder (surrogate fine-particle source) |
| Sample coupons | 10 cm × 10 cm fabric squares |
| Test chamber | Sealed 22.8 × 16 × 17.5 cm enclosure, custom-ported |
| Sampling scheme | Paired "upstream" and "downstream" lines to dual monitors |
| Efficiency metric | `Efficiency (%) = (C_before − C_after) / C_before × 100` |

Fabrication meant drilling and sealing rigid sampling ports into the chamber, plumbing flexible and silicone tubing into two EMSL filter holders, and reinforcing every joint with silicone sealant and washers. Leak-free sealing was the critical design constraint: any bypass path around the fabric sample would inflate the apparent efficiency and invalidate the result.

## Test methodology

1. Zero-calibrate both DustTrak monitors before each session.
2. Mount and label a 10 × 10 cm fabric coupon in the filter holder.
3. Introduce a controlled talcum aerosol pulse into the chamber.
4. Capture peak concentrations on the upstream ("before") and downstream ("after") monitors across all PM bands.
5. Compute filtration efficiency per band; screen single fabrics, then test the strongest performers in 2- and 3-layer combinations.

## Results

Screening 30 fabrics surfaced several strong single-layer materials, but the decisive gains came from **layering** — stacking complementary fabrics to capture particles across size ranges.

| Configuration | PM1 (&lt;1 µm) efficiency | Total mass efficiency |
|---|---|---|
| Pure silk — single layer (#27) | 84.4% | — |
| Green felt sheet, 100% polyester (#25) | 87.8% | — |
| Lightweight corduroy (#23 / #24) | 94.4% | — |
| **Silk + lightweight jean + silk (#27 + #26 + #27)** | **98.9%** | **99.4%** |
| **Silk + felt + silk (#27 + #25 + #27)** | — | **99.4%** |
| N-95 reference (#16) | — | 99.998% |

Key findings:

- **Silk punched far above its weight.** An extremely thin single layer of pure silk captured **84.4% of sub-micron (PM1) particles** on its own — the ideal outer layer in a stack.
- **The winning design was a triple layer.** Silk + lightweight jean + silk reached **99.4% total** and **98.9% PM1** efficiency; a silk + felt + silk stack matched **99.4% total**.
- **My hypothesis was disproven.** I predicted the thick, opaque black felt sheet would filter best. It did not — thickness and opacity were poor predictors, and **material choice plus layering strategy mattered far more than bulk.**

## The final product

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>Optimized mask filter — Silk / Lightweight Jean / Silk (3-layer)</strong><br>
99.4% total particulate filtration &nbsp;•&nbsp; 98.9% sub-micron (PM1) capture &nbsp;•&nbsp; built entirely from accessible household materials.
</div>

Benchmarked against a medical N-95 (99.998% total), the engineered household stack closed the overwhelming majority of the performance gap using materials most people already own — meeting the core goal: an accessible, high-performance mask for people who cannot obtain or afford an N-95.

## Engineering challenges &amp; limitations

- **Layer-count ceiling.** The filter holder physically accommodated a maximum of three thick fabric layers, constraining the design space; a larger fixture would enable deeper stacks.
- **Instrument saturation.** The monitors capped at 150 mg/m³ and halted the run whenever a sample passed too much aerosol — a measurement-range limit I nicknamed "the 150 bomb" — forcing repeat tests.
- **Surrogate aerosol.** Talcum powder stands in for viral-scale aerosols, so the results indicate relative performance rather than certified viral filtration.

## Future work

- Independent laboratory validation of the top-performing configurations for certified efficiency figures.
- A larger test fixture to evaluate 4+ layer stacks alongside pressure-drop (breathability) trade-offs.
- Higher-ceiling instrumentation to characterize weak samples without saturation.

---

**Awards:** Hamilton Academy of Dentistry Award — Second Place, John W. Howard Materials Research Award, Silver Merit Award, Bay Area Science &amp; Engineering Fair (BASEF) 2021.

**Engineering skills:** experimental design · test-apparatus fabrication · aerosol instrumentation (TSI DustTrak DRX) · materials characterization · data analysis · design of experiments · public-health engineering.
