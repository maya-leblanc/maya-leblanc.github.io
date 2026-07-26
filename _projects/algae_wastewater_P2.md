---
layout: page
title: Wastewater Filtration System — Material Selection and Life-Cycle Design
description: A team materials-engineering project using Ashby performance indices, decision matrices, and life-cycle eco-audits to select a Nylon-6 filter (92% cyanobacteria rejection, 80% porosity) for a wastewater treatment plant in the Philippines. McMaster ENGINEER 1P13, 2026.
img: assets/img/projects/wastewater.png
importance: 4
category: engineering
related_publications: false
---

A quantitative materials-engineering and sustainability project. My five-person team designed the filter for the primary-treatment stage of a wastewater plant tackling toxic cyanobacteria blooms — but the real work was **choosing the right material by the numbers**. We used Ashby material performance indices, decision matrices, porosity mechanics, and full life-cycle eco-audits to converge on **Nylon-6**, balancing cost, carbon footprint, durability, and a **92% algae-rejection rate**, then validated it survived real underwater operating conditions.

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">92%</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Cyanobacteria rejection<br>(vs. 80% alternatives)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">80%</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Engineered filter<br>porosity</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">5</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Fiber candidates ranked<br>by material index</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">10 yr</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Projected filter<br>service life</div>
  </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/wastewater_filter.jpg" title="Wastewater filtration material selection" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Nylon-6 fiber filter selected through Ashby material-index analysis for cyanobacteria removal in wastewater primary treatment.
</div>

## The problem

A treatment pond in Tampakan, Philippines, was choking with toxic cyanobacteria (blue-green algae) that was harming local livestock relying on the water. Our brief: engineer a filter for the plant's **primary-treatment stage** (sedimentation and skimming) that removes the algae reliably at industrial scale. Because a wastewater plant deploys these filters in huge numbers, the design was cost-driven — but it also had to survive continuous underwater operation and minimize environmental harm in a project literally about protecting an ecosystem.

## Objectives &amp; constraints

| Requirement | Target |
|---|---|
| Primary objective | Minimize cost (large-scale deployment) |
| Secondary objective | Minimize production CO₂ footprint |
| Property limit | Excellent water durability |
| Property limit | Good abrasion resistance |
| Performance | High flow rate (achieved via porosity) |

## Material selection: the Ashby method

Rather than guessing, we selected the filter material quantitatively using **material performance indices (MPIs)** — the ratios that identify which material maximizes performance for a given objective. We split the index space across the team and ranked candidate fibers on each:

- `√E / (Cₘ·ρ)` — stiffness per unit cost
- `σ^⅔ / (Cₘ·ρ)` — strength per unit cost
- `√E / (CO₂·ρ)` — stiffness per unit carbon footprint *(my index)*
- `σ^⅔ / (CO₂·ρ)` — strength per unit carbon footprint

*(where E = Young's modulus, σ = yield strength, ρ = density, Cₘ = cost/kg)*, with **excellent water durability** and **good abrasion resistance** applied as hard property limits so any candidate that couldn't survive submersion was screened out.

Ranking fiber candidates — Nylon-6, Dacron, Vectran, PAN, UHMWPE, flax — across all four indices produced three finalists (Vectran, Dacron, PAN), which we scored in a weighted decision matrix on access, corrosion resistance, maintainability, cost, and shape retention.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>Final selection — Nylon-6 (polyamide fiber).</strong> It topped the strength-per-cost index and ranked highly across the others, and external research showed a decisive edge: <strong>92% cyanobacteria rejection versus ~80%</strong> for the alternatives. Combined with its low cost, wide availability, corrosion resistance, and the lowest filter mass of the finalists (1.40 kg), it best served the primary cost objective while meeting every property limit.
</div>

| Nylon-6 property | Value |
|---|---|
| Young's modulus | 4.5 GPa |
| Yield strength | 825 MPa |
| Density | 1140 kg/m³ |
| Specific carbon footprint | 8.09 kg/kg |
| Pore size | 0.45 µm |
| Cyanobacteria rejection | 92% |

## Porosity &amp; mechanical validation

A filter isn't a solid block — it's mostly holes. We engineered the filter to an **80% porosity** (the industry standard, balancing flow rate against strength) and then recomputed the mechanical properties to confirm the porous material still held up. At 80% porosity the **effective yield strength dropped to 33 MPa** and the **effective Young's modulus to 0.18 GPa** — both still plotting above our MPI guideline on the Granta Ashby chart, confirming Nylon-6 remains a viable filter material even riddled with pores and running underwater.

## Life-cycle &amp; sustainability analysis

We ran a **Granta Eco-Audit** on the top three materials to quantify their environmental footprint across materials, manufacturing, transport, and end-of-life. For Nylon-6 the life-cycle totals came to **184,000 MJ of energy and 13,900 kg of CO₂**, dominated by the raw-materials phase (67% of energy) — while transport was **negligible (0.5%)** thanks to the short China-to-Philippines shipping distance (~2,000 km). Nylon-6's higher production footprint was a real trade-off against the secondary CO₂ objective, but its recyclability, 10-year service life, low mass, and cost advantage made it the right call for a cost-primary, large-scale facility. Increasing porosity also directly cuts footprint — less material per filter means less embodied energy and carbon.

## Regulatory &amp; deployment context

Because the system targets a specific jurisdiction, we grounded it in real Philippine regulation — the Clean Water Act of 2004, DENR effluent standards (total-suspended-solids limits by water class), material-acquisition permitting for sand/gravel, the Philippine Electrical Code, and renewable-energy statutes — so the design would be legal, sourceable, and scalable rather than a lab abstraction.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.5rem 0;">
<strong>My contributions — Subject Matter Expert (Team Tues-20).</strong>
<ul style="margin: 0.5rem 0 0 0;">
<li>Researched the filtration-technique design space (mechanical filtration, coagulation-flocculation, biofiltration) that framed the team's approach.</li>
<li>Owned the <strong>stiffness-per-carbon material index</strong> (<code>√E / (CO₂·ρ)</code>) and its full candidate-fiber ranking.</li>
<li>Built the life-cycle diagram and contributed to the Granta eco-audit and final material selection.</li>
</ul>
</div>

---

**Context:** McMaster University · ENGINEER 1P13 — Design Project 2, Wastewater Filtration · March 2026.

**Engineering skills:** materials selection (Ashby method / performance indices) · Granta EduPack &amp; Eco-Audit · life-cycle analysis · decision-matrix analysis · porosity &amp; mechanical property modeling · sustainability engineering · regulatory analysis · team-based engineering design.
