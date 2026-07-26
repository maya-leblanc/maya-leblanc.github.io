---
layout: page
title: Carbon Capture via Catalyzed Photosynthesis to Promote Crop Growth
description: Designed and built airtight greenhouse enclosures to test catalyzed photosynthesis, achieving 4.3× higher CO₂ uptake and 35.2 mg/plant/day of incremental capture — then modeled national-scale climate impact and full business feasibility. BASEF & CWSF 2022; published in the Canadian Science Fair Journal.
img: assets/img/projects/carbon.png
importance: 4
category: research
related_publications: true
---

An environmental- and systems-engineering project spanning hardware, data, and economics: I designed and fabricated sealed greenhouse enclosures with integrated CO₂, lighting, airflow, water, and sensing subsystems, ran a three-cycle experiment to prove that applied CO₂ **plus** an applied light source accelerates photosynthetic carbon capture, then modeled the national-scale climate impact and built a company-level business case. The catalyzed process captured CO₂ at **4.3× the rate** of the CO₂-only condition — an incremental **35.2 mg of CO₂ per plant per day**.

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">4.3×</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Higher CO₂ uptake vs.<br>CO₂-only condition</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">336.9</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">ppm/day incremental<br>CO₂ consumption</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">35.2 mg</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Extra CO₂ captured<br>per plant, per day</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">2.6 t</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Projected CO₂ captured<br>per acre, per year</div>
  </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/carbon_capture.jpg" title="Carbon capture research" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Custom-built airtight greenhouse enclosure with integrated CO₂, lighting, airflow, water, and sensing subsystems.
</div>

## The problem

Industrial carbon capture pulls CO₂ out of factory emissions, but the captured gas has to *go* somewhere — often into pressurized tanks or deep geologic storage, where a future leak would release it all over again. I wanted a route that consumes captured CO₂ productively instead of merely storing it: **feed industrial CO₂ into greenhouses to accelerate crop growth, turning a waste stream into food and permanent drawdown.**

## Engineering objective

Prove, under controlled conditions, that combining applied CO₂ with an applied light source measurably increases a plant's photosynthetic CO₂ consumption — then quantify that gain and evaluate whether it scales to a meaningful climate and commercial impact.

## Design &amp; build: sealed greenhouse enclosures

The experiment compared three garden-cress specimens under different atmospheres:

| Specimen | Conditions |
|---|---|
| **Specimen 1** — control | Ambient air, open room |
| **Specimen 2** | Sealed enclosure + applied CO₂ |
| **Specimen 3** | Sealed enclosure + applied CO₂ + applied grow light |

Specimens 2 and 3 needed airtight enclosures, so I designed and fabricated them from repurposed CNC-machine housings. Each build integrated five subsystems that all had to pass through the shell **without breaking the air seal** — the central engineering constraint, since any leak corrupts the CO₂ measurement:

- **Compression-sealed lid** — aluminum channel frame, weather stripping, and corner angle brackets with tightening bolts to clamp the lid gas-tight.
- **CO₂ delivery** — SodaStream cylinder metered through a sealed hose-barb inlet; target concentration **3,000–4,000 ppm** (Health Canada's recommended indoor maximum is 3,500 ppm).
- **Lighting** — a 15 W LED grow light for the catalyzed specimen.
- **Airflow** — two internal fans, wired out through sealed hose-barb penetrations to external USB transformers, to keep the atmosphere well mixed before sampling.
- **Internal irrigation** — an external Y-fitting feeding a through-lid line to a T-fitting and twin semicircular tubes that deliver water directly to the pots without opening the enclosure.
- **Sensing** — a TSI Q-Trak 7575-X with an 982 probe, sealed through the lid so CO₂ could be measured without breaking containment.

Every joint, corner, and penetration was sealed with silicone and cured before testing.

## Engineering challenges &amp; iteration

I ran the experiment as three cycles — Test 1, 2, and 3 — treating each failure as a design input for the next build:

- **Faulty CO₂ sensors.** The original sensors wouldn't register rising CO₂. I confirmed the fault by renting a high-performance Q-Trak meter, then switched the whole measurement chain over to it. When the probe's sensors turned out to be partly blocked by the PVC coupling I'd added to the lid, I replaced the coupling with a custom donut-shaped probe seal that lets the full probe length enter the enclosure — which stabilized the readings.
- **Irrigation leaks.** The internal water lines kept slipping off the pots and spilling into the sealed chamber. I added couplings and T-connectors to the tube ends so they brace against the pot walls and stay put.
- **Condensation &amp; mould.** Daily watering drove the humidity high enough to fog the enclosures and grow root-eating mould — which, I discovered mid-project, actually *emits* CO₂ and was corrupting my data. I solved it by dialing back watering, relocating the enclosures away from the cold window driving condensation, and staging in additional desiccant until condensation and mould disappeared.

## Results

Over Test 3, I measured the daily CO₂ drawdown for each sealed specimen and computed the incremental effect of the catalysts:

| Configuration | Daily CO₂ consumption |
|---|---|
| Specimen 2 — applied CO₂ only | 103.3 ppm/day |
| **Specimen 3 — applied CO₂ + grow light** | **440.2 ppm/day** |
| **Incremental gain from catalysis (S3 − S2)** | **336.9 ppm/day → 35.2 mg CO₂ / plant / day** |

Key findings:

- **The light source was the decisive catalyst.** Adding a grow light on top of elevated CO₂ raised daily carbon uptake to **440.2 ppm/day — roughly 4.3× the 103.3 ppm/day** of the CO₂-only specimen.
- **Quantified drawdown.** Converting concentration to mass using the enclosure volume and the molar mass of CO₂, the catalyzed specimen captured an extra **35.2 mg of CO₂ per plant per day** beyond baseline.
- **Hypothesis supported.** Because Specimen 3's reduction so far exceeded Specimen 2's, the increased carbon consumption is attributable to a genuinely higher photosynthesis rate driven by the applied CO₂ and light — not measurement noise.

## Scaling analysis: national impact

I extrapolated the measured rate to estimate real-world greenhouse deployment. A one-acre catalyzed crop projects to **~2.6 tonnes of additional CO₂ captured per year**. Set against Canada's emissions (68.9 M hectares of farmland available):

| Climate benchmark | Greenhouse land required | Share of Canada's farmland |
|---|---|---|
| Offset all road-transport emissions (137 Mt/yr) | ~21.3 M hectares | 31% |
| Meet Canada's 2030 target (299 Mt reduction) | ~46.5 M hectares | 68% |

Covering a third to two-thirds of national farmland isn't realistic, but the analysis frames the honest scale of the lever — and shows that partial deployment still delivers meaningful drawdown while producing food.

## Feasibility: business case

To test commercial viability I built a company-level plan around designing, installing, and servicing these greenhouses for farmers, funded through government incentives and carbon-emitter contributions:

- **Cost structure** — ~$830K/year in staffing (service technicians across every province, sales, government lobbying, project management, accounting), for total operating costs of roughly **$970K–$1M/year**.
- **Pricing model** — installations quoted at contractor cost plus 10% overhead and 10% profit (e.g. $3/ft² → $3.60/ft²); servicing at about **$5,000/month per greenhouse**.
- **Runway** — the model implies a **3+ year path to break-even** as service contracts ramp, and positions the product against geologic carbon sequestration as a leak-free, food-producing alternative.

## Limitations &amp; future work

Because my home wasn't a sealed environment, Specimen 1 couldn't serve as a true CO₂-consumption control — Specimen 2 (CO₂ only) is the more rigorous baseline, which is why the incremental result is measured against it. Future work would test additional crop types (each with its own uptake rate), characterize the breathability/pressure trade-offs of scaled enclosures, and validate the mass-capture figures in a controlled lab.

---

**Recognition:** Bay Area Science &amp; Engineering Fair (BASEF) 2022 · Canada-Wide Science Fair (CWSF) 2022.

**Published:** Canadian Science Fair Journal.

**Engineering skills:** apparatus design &amp; fabrication · systems integration (CO₂, lighting, airflow, irrigation, sensing) · sealed-enclosure engineering · instrumentation (TSI Q-Trak) · iterative design &amp; troubleshooting · data analysis · techno-economic modeling · environmental engineering.
