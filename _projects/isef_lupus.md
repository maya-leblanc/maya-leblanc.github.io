---
layout: page
title: Genetic Analysis of Monocyte and T Lymphocyte Cells for Lupus Diagnostics
description: Independent bioinformatics research identifying a novel gene expression signature and diagnostic criteria for systemic lupus erythematosus (SLE).
img: assets/img/projects/lupus_research.png
importance: 1
category: research
related_publications: false
---

Independent research project analyzing microarray gene expression data from CD16+ monocytes, CD16- monocytes, and CD4+ T lymphocytes to identify a novel gene expression signature for systemic lupus erythematosus (SLE), and to establish diagnostic criteria that could support a single-test diagnostic tool.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/lupus_research.png" title="Genetic analysis of SLE gene expression" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Genetic analysis of CD16+ monocyte, CD16- monocyte, and CD4+ T lymphocyte gene expression to identify a novel SLE diagnostic signature.
</div>

**Tools:** bioinformatics, biostatistics, Python, Minitab, gene expression microarray analysis.

**Presented at:** BMED062, independent research

---

### The Problem

Systemic lupus erythematosus (SLE) is an incurable autoimmune disease in which the immune system attacks the body's own tissues, causing widespread inflammation and organ damage. It carries an annual mortality rate of 18.6 per 1,000 diagnosed persons and is often called "the great imitator" because its symptoms overlap with dozens of other conditions. As a result, diagnosis takes an average of six years, relies on a patchwork of lab tests, biopsies, and imaging, and drives up healthcare costs through repeated and often inconclusive testing. **No single test currently exists to diagnose SLE.**

### Research Goals

1. Evaluate gene expression in CD16+ monocytes, CD16- monocytes, and CD4+ T lymphocytes to identify gene expression signatures unique to SLE, with the goal of improving diagnostic accuracy and speed.
2. Determine whether any identified signature could serve as the basis for a diagnostic tool.

**Hypothesis:** Comparing gene expression across these three cell types between healthy individuals and SLE patients will reveal expression differences unique to SLE (rejecting the null hypothesis of no difference).

### Methodology

**Step I — Data Acquisition and Normalization**
Raw microarray gene probe data (54,675 probes across 3 cell types) was obtained from the Gene Expression Omnibus (GEO), NCBI, using datasets GDS4888 (CD4+ T lymphocytes), GDS4889 (CD16- monocytes), and GDS4890 (CD16+ monocytes). Data was normalized with Affymetrix GCOS software, filtered for differentially expressed probe sets in BioRetis, cross-referenced against published interferon-regulated transcript lists, and clustered using Genesis.

**Step II — Statistical Significance Testing**
Gene probe values for healthy versus SLE cohorts were compared using one-tailed t-tests (heteroscedastic or homoscedastic, selected via a 1.5 variance-ratio threshold) across all 54,675 probes for each cell type. The five gene probes with the lowest p-values across all three cell types were selected for further evaluation, with resulting p-values ranging from 1.9×10⁻⁴ to 7.3×10⁻⁷ — confirming statistically significant differences between cohorts.

**Step III — Identifying a Novel Gene Expression Signature**
Of the five candidate genes, NFYC and STAT1 were excluded as transcription-regulation genes rather than genes tied to vital cellular function. The remaining three — **ATP6V0C, UBA1, and TGFB1** — were cross-referenced against published SLE-associated gene databases and confirmed as *not currently known to be associated with SLE*. Quantile-quantile plots (generated via a custom Python–Minitab interface) confirmed the data followed a normal distribution, validating the statistical approach.

**Step IV — Establishing Diagnostic Criteria**
For each of the three genes, a hypothetical gene probe value was iteratively introduced into the CD16- monocyte dataset to model the relationship between probe value and statistical significance. This produced minimum and maximum gene probe value thresholds (at p = 1×10⁻⁴) that define a diagnostic range for each gene.

### Key Findings

| Gene | Best p-value (CD16- monocytes) | Diagnostic range (probe value) |
|---|---|---|
| UBA1 | 4.6×10⁻⁶ | 376 – 699 |
| TGFB1 | 7.3×10⁻⁷ | 420 – 721 |
| ATP6V0C | 1.4×10⁻⁶ | 785 – 1312 |

The **CD16- monocyte cell type** produced the strongest statistical separation between healthy and SLE cohorts across all three genes, making it the most diagnostically informative cell type identified in this study.

> Gene probes associated with ATP6V0C, UBA1, and TGFB1 in CD16- monocytes represent a novel gene expression signature for the identification of SLE — the first study to establish this specific signature and associated diagnostic criteria.

### Conclusions

- A statistically significant difference (p < 1.4×10⁻⁶) in gene probe values for ATP6V0C, UBA1, and TGFB1 was confirmed between healthy and SLE cohorts across all three cell types, rejecting the null hypothesis.
- CD16- monocytes were identified as the strongest indicator of this difference (1.4×10⁻⁶ < p < 7.3×10⁻⁷).
- These three genes, in CD16- monocytes, constitute a novel gene expression signature not previously documented in SLE literature.
- Diagnostic criteria based on this signature's high/low probe value thresholds (p < 0.0001) were developed as the basis for a potential single-test diagnostic tool.

### Societal Impact & Future Research

A validated diagnostic signature could meaningfully shorten the current six-year average time to SLE diagnosis, reduce costs associated with redundant testing, and get patients into appropriate treatment faster. Extending this work would require validating the signature against a larger cohort to improve statistical power, and longer-term studies involving asymptomatic individuals to test whether the signature can also indicate predisposition to SLE before onset.

---

*Special thanks to Dr. Mathieu Lupien, Ornela Kljakic, and Dr. Guillaume Bourque for their guidance in defining this project's research direction.*
