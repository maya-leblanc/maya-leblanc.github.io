---
layout: page
title: A Novel Gene Signature & Diagnostic Tool for Lupus (SLE)
description: Published bioinformatics research analyzing 54,675 gene probes across three immune cell types to identify a novel 5-gene expression signature for systemic lupus erythematosus, and diagnostic criteria for a potential single blood-test tool. International Journal of High School Research, 2025.
img: assets/img/projects/isef.png
importance: 1
category: research
related_publications: false
---

Peer-reviewed, published computational-biology research. I analyzed **54,675 gene probes** across three immune cell types from lupus patients and healthy controls, built a full statistical pipeline to isolate the genes most strongly associated with the disease, and identified a **novel five-gene expression signature** in CD16⁻ monocytes, then translated it into diagnostic value ranges for a potential single blood-test tool. Systemic lupus erythematosus (SLE) currently has **no single diagnostic test** and takes an average of six years to diagnose; this work is a step toward changing that.

<div style="border-left: 4px solid var(--global-theme-color); padding: 0.5rem 1rem; margin: 1.25rem 0;">
<strong>Published</strong> — <em>International Journal of High School Research</em>, vol. 7, no. 9 (2025) · DOI: <a href="https://doi.org/10.36838/v7i9.80" target="_blank" rel="noopener noreferrer">10.36838/v7i9.80</a>
</div>

<div class="row text-center mt-4 mb-4">
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">54,675</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Gene probes screened<br>per cell type</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">5</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Novel signature genes<br>identified</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">7.3×10⁻⁷</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Strongest p-value<br>(statistical significance)</div>
  </div>
  <div class="col-6 col-md-3 mb-3">
    <div style="font-size: 2.2rem; font-weight: 700; color: var(--global-theme-color); line-height: 1;">1</div>
    <div style="font-size: 0.8rem; opacity: 0.8;">Blood test vs. today's<br>6-year diagnosis</div>
  </div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/isef.png" title="Genetic analysis of SLE gene expression" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gene-expression analysis across CD16⁺ monocyte, CD16⁻ monocyte, and CD4⁺ T-lymphocyte cell types to identify a novel SLE diagnostic signature.
</div>

## The problem

Systemic lupus erythematosus is an incurable autoimmune disease in which the immune system attacks the body's own tissues, driving inflammation and organ damage across the joints, skin, kidneys, lungs, brain, and blood vessels. It is nicknamed **"the great imitator"** because its symptoms overlap with dozens of other conditions, which is why diagnosis takes an average of **six years** from first symptoms and relies on a patchwork of medical history, physical exams, ANA blood tests, and biopsies that mostly *rule out* other diseases rather than confirm SLE. **No single conclusive test exists.** That delay costs patients years of untreated progression and burdens the healthcare system with repeated, often inconclusive testing.

## Objective &amp; hypothesis

Evaluate gene expression across CD16⁺ monocytes, CD16⁻ monocytes, and CD4⁺ T lymphocytes to find an expression signature unique to SLE, and determine whether that signature could form the basis of a diagnostic tool. **Hypothesis:** comparing expression between healthy and SLE cohorts across these three cell types will reveal differences unique to SLE, rejecting the null hypothesis of no difference. The work is deliberately novel in focusing on **CD16⁻ (classical) monocytes**, a subset far less explored in SLE diagnostics than the pro-inflammatory CD16⁺ subset.

## Methodology

I built and ran the full analysis pipeline end to end:

| Element | Detail |
|---|---|
| Data source | Gene Expression Omnibus (NCBI) — datasets GDS4888, GDS4889, GDS4890 |
| Scale | 54,675 gene probes × 3 immune cell types |
| Cohort | Female SLE patients vs. healthy controls (aged 24–29) |
| Preprocessing | Normalization (Affymetrix GCOS), differential-expression filtering (BioRetis), hierarchical clustering (Genesis) |
| Significance testing | One-tailed t-test; hetero- or homoscedastic selected by a 1.5 variance-ratio threshold; p < 0.0001 |
| Distribution validation | Quantile-quantile plots via a custom Python–Minitab interface |
| Toolchain | Excel, Affymetrix GCOS, BioRetis, Genesis, Python 3.12, Minitab, VS Code |

Every one of the 54,675 probes in each dataset was variance-tested to choose the correct t-test, then p-value-ranked to surface the strongest signals — a large-scale, reproducible statistical workflow. Quantile-quantile plots confirmed the data was statistically appropriate (approximately normal) for the analysis.

## Results: a novel five-gene signature

The five probes with the most significant differences between healthy and SLE cohorts mapped to the genes **ATP6V0C, UBA1, TGFB1, STAT1, and NFYC**, with p-values spanning **1.9×10⁻⁴ to 7.3×10⁻⁷**. The **CD16⁻ monocyte** cell type produced the most consistent, statistically robust separation across all probes (p-values from **1.4×10⁻⁶ to 7.3×10⁻⁷**), making it the most diagnostically informative cell type.

Benchmarking these genes against a published catalog of 50+ known SLE-associated genes confirmed that **none of the five had previously been linked to SLE** — establishing a genuinely novel expression signature.

| Gene | Cellular role | Diagnostic range (CD16⁻, p < 10⁻⁴) |
|---|---|---|
| ATP6V0C | V-ATPase proton pump; cellular pH balance | 785 – 1312 |
| UBA1 | Ubiquitin-activating enzyme; protein turnover | 376 – 699 |
| TGFB1 | TGF-β1 cytokine; immune regulation | 420 – 721 |
| STAT1 | Transcription factor; interferon signaling | 4004 – 4017 |
| NFYC | Transcription factor; gene-expression regulation | 254 – 320 |

## From signature to diagnostic tool

For each gene, I iteratively modeled how the probe value relates to statistical significance, deriving the high/low expression thresholds (at p = 1×10⁻⁴) that define a diagnostic range. That yields a concrete, four-step test concept:

1. Draw a single blood sample.
2. Isolate CD16⁻ monocytes.
3. Measure expression of the five signature-gene probes.
4. Compare against the established ranges to flag SLE.

A single-sample test like this could compress the current six-year diagnostic odyssey into one blood draw, getting patients to treatment sooner while cutting the cost of redundant testing. (The tool is a validated *criteria framework*; clinical deployment would require large-cohort validation.)

## Impact &amp; future work

A validated signature could shorten time-to-diagnosis, reduce healthcare costs, and speed treatment. The natural extensions: validate against a larger cohort to strengthen statistical power beyond this study's small sample, and run longitudinal studies including asymptomatic individuals to test whether the same signature can flag genetic *predisposition* to SLE before onset, a quantitative early-warning capability that, to my knowledge, does not yet exist.

<div style="font-size: 0.85rem; opacity: 0.85; margin-top: 1rem;">
Research direction guided by Dr. Mathieu Lupien, Ornela Kljakic, and Dr. Guillaume Bourque, with expert review by Dr. Dawn Bowdish, Dr. Jessica A. Breznik, and Dr. Konstantinos Tselios.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0 text-center">
        <a href="https://doi.org/10.36838/v7i9.80" target="_blank" rel="noopener noreferrer" class="btn btn-outline-dark">Read the published paper</a>
    </div>
</div>

---
**Awards & Recognition**:
- BASEF 2024: Drs. Ranjan Sur & Monalisa Sur Award — Best Intermediate/Senior Project in the Fair, Best in Fair — Primary Fluid Systems Pinnacle Award, International Science and Engineering Fair Trip Award, Sanofi Biogenius Canada Award, Mohawk College Mathematics Award — Senior, Gold Merit Award.
- CWSF 2024: CWSF Silver Merit Award
- ISEF 2024: Fourth Place Grand Award — Biomedical and Health Sciences

**Links**: https://isef.net/project/bmed062-novel-gene-signatures-and-diagnostic-tool-for-sle-pwxxyx, partner.projectboard.world/ysc/project/analysis-of-cd16-cd16-and-cd4-t-cells-to-identify-novel-gene-signatures-and-diagnostics-for-sle. 

**Engineering &amp; research skills:** bioinformatics · transcriptomic data analysis · biostatistics (t-tests, variance modeling, Q-Q validation) · large-scale data processing (54,675 probes × 3 datasets) · Python · Minitab · custom tool integration · scientific writing &amp; peer-reviewed publication.
