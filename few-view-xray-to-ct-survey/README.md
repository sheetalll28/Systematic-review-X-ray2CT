# A Systematic Review of Few-View X-Ray-to-CT Reconstruction: From Single-View Learning to Diffusion-Based 3D Generation


[![Paper Status](https://img.shields.io/badge/Status-Under%20Preparation-orange.svg)]()
[![Survey](https://img.shields.io/badge/Type-Survey%20%2F%20Literature%20Review-green.svg)]()

---

## Project Type

> **This repository is a research artifact supporting an academic survey paper.** It does **not** propose a novel reconstruction algorithm, nor does it contain deep learning training code. All materials here serve as structured documentation, metadata, and tooling for a systematic literature review on few-view X-ray-to-CT reconstruction methods.

---

## Overview

Reconstructing 3D computed tomography (CT) volumes from a limited number of X-ray projections is a long-standing challenge in medical imaging. Traditional analytic and iterative algorithms require hundreds of projections; recent deep learning approaches aim to achieve comparable quality from drastically fewer views — sometimes as few as a single radiograph.

This survey provides a comprehensive, structured review of the rapidly evolving landscape of **few-view X-ray-to-CT reconstruction**, covering:

| Category | Scope |
|---|---|
| **GAN-based methods** | Generative adversarial networks for volumetric synthesis |
| **Transformer-based methods** | Vision transformers and attention mechanisms for 3D reconstruction |
| **Neural field methods** | Neural radiance fields (NeRF) and implicit representations adapted for CT |
| **Diffusion-based methods** | Score-based and denoising diffusion models for 3D generation from sparse views |

The survey also examines **benchmark datasets**, **domain gap challenges** (synthetic vs. clinical data), **evaluation metrics**, and **open research questions**.

---

## Novelty & Gap This Survey Fills

> **No systematic survey exists that covers the post-2023 generative era of X-ray-to-CT reconstruction.**

The only comprehensive prior taxonomy of 2D-to-3D X-ray reconstruction is **Maken & Gupta (2023)** *(Arch. Comput. Methods Eng., 30:85–114)*, which systematically reviewed methods up to approximately **2020–2021** — covering classical statistical shape models (SSMs), parametric approaches, contour deformation, and early CNNs.

Since that landmark survey, the field has undergone a **fundamental paradigm shift** driven by three transformative generative frameworks:

| Era | Period | Representative Methods | What Changed |
|---|---|---|---|
| **GAN era** | 2021 – 2024 | X2CT-GAN, CVAE-GAN, TRCT-GAN, DP-GAN+B, AP2CT-GAN, PTX2CT-GAN | End-to-end volumetric synthesis from 1–2 X-rays; disease-specific architectures |
| **Diffusion era** | 2024 – 2026 | DX2CT, DVG-Diffusion, 3D Diffusion (Yoon) | Stable training, iterative refinement, position-aware conditioning; now state-of-the-art |
| **Neural Implicit / NeRF era** | 2022 – 2026 | MedNeRF, X2BR | Continuous implicit 3D fields; single X-ray → arbitrary CT projections; near-zero radiation limit |

This survey is the **first work to systematically cover all three post-2023 generative eras together**, providing:

- A unified chronological taxonomy spanning **1990 → 2026** across four eras.
- Detailed architecture diagrams, mathematical formulations, and quantitative comparison tables for every reviewed method.
- A cross-era comparative analysis highlighting the progressive shift from single-view constraints to diffusion-based state-of-the-art.
- An identification of six open challenge areas and concrete future research directions.

---

## Repository Contents

```
few-view-xray-to-ct-survey/
│
├── README.md                  ← This file
├── LICENSE                    ← MIT License
├── .gitignore                 ← Git ignore rules for LaTeX, Python, etc.
├── requirements.txt           ← Python dependencies for helper scripts
│
├── literature/                ← Source literature and reference papers
│   ├── base_paper.pdf         ← The foundational base paper for this survey
│   └── surveyed_papers/       ← PDFs of reviewed papers categorized by methodology
│       ├── diffusion/
│       ├── gan/
│       ├── nerf/
│       └── extra/
│
├── report/                    ← LaTeX source for the survey manuscript
│   ├── main.tex               ← Master LaTeX document
│   ├── references.bib         ← BibTeX bibliography
│   └── output/
│       ├── CV_REPORT.pdf      ← The fully compiled survey/report
│       └── README.md          ← Instructions for viewing/generating the report
│
├── paper_metadata/            ← Curated paper lists and screening notes
│   ├── included_papers.md
│   ├── core_papers.md
│   ├── supporting_papers.md
│   ├── background_papers.md
│   └── screening_notes.md
│
├── tables/                    ← Extracted comparison tables (CSV)
│   ├── comparison_table_template.csv    ← All 14 methods across all eras (master table)
│   ├── gan_methods_comparison.csv       ← GAN-era methods detailed comparison
│   ├── diffusion_methods_comparison.csv ← Diffusion-era methods detailed comparison
│   └── nerf_neural_implicit_comparison.csv ← NeRF & neural implicit methods comparison
│

├── docs/                      ← Project documentation and methodology
│   ├── project_scope.md
│   ├── inclusion_exclusion_criteria.md
│   ├── search_strategy.md
│   └── submission_notes.md
│
├── resources/                 ← Curated external links
│   ├── official_code_links.md
│   ├── dataset_links.md
│   └── reading_list.md
│
└── scripts/                   ← Lightweight helper scripts (Python)
    ├── generate_method_timeline.py
    ├── make_comparison_chart.py
    └── clean_bib_stub.py
```

---

## How to Use

### 1. Read the Compiled Survey

- The full compiled PDF is at **[`report/output/CV_REPORT.pdf`](report/output/CV_REPORT.pdf)**.
- The LaTeX source is the single self-contained file [`report/main.tex`](report/main.tex).
- All references are in [`report/references.bib`](report/references.bib).

### 2. Explore the Comparison Tables

- [`tables/comparison_table_template.csv`](tables/comparison_table_template.csv) — master table of all 14 reviewed methods.
- [`tables/gan_methods_comparison.csv`](tables/gan_methods_comparison.csv) — GAN-era details.
- [`tables/diffusion_methods_comparison.csv`](tables/diffusion_methods_comparison.csv) — diffusion-era details.
- [`tables/nerf_neural_implicit_comparison.csv`](tables/nerf_neural_implicit_comparison.csv) — NeRF/neural implicit details.

### 3. Explore the Paper Metadata

- [`paper_metadata/included_papers.md`](paper_metadata/included_papers.md) explains the paper categorization scheme.
- Core, supporting, and background papers are listed in their respective files.

### 4. Compile the LaTeX Report

```bash
cd report/
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Or open `report/main.tex` directly in Overleaf, TeXstudio, or VS Code with the LaTeX Workshop extension.

### 4. Run Helper Scripts

```bash
pip install -r requirements.txt
python scripts/generate_method_timeline.py
python scripts/make_comparison_chart.py
python scripts/clean_bib_stub.py
```

These scripts produce simple visualisations and perform basic bibliography housekeeping. They do **not** train or evaluate any machine learning models.

---

## Survey Scope

This review focuses on **learning-based methods** for reconstructing CT volumes from **few X-ray projections** (typically 1–10 views). The scope includes:

- Methods published primarily between **2018 and 2025**.
- Approaches targeting **medical CT reconstruction** (chest, spine, knee, head, etc.).
- Deep learning architectures: CNNs, GANs, transformers, neural implicit representations, and diffusion models.
- Evaluation on both **synthetic** (e.g., digitally reconstructed radiographs) and **clinical** datasets.

The survey does **not** cover:

- Traditional analytic reconstruction (e.g., FBP, ART) except as baselines.
- Sparse-view CT from many (>10) projections (a related but distinct problem).
- Non-medical applications (e.g., industrial CT, baggage scanning) unless directly relevant.

---

## Future Work

This repository currently supports the **survey manuscript preparation**. In future iterations, we plan to:

- Add a **reproducibility benchmark** comparing open-source implementations of surveyed methods.
- Include a **standardised evaluation protocol** with shared dataset splits and metrics.
- Provide a **living document** that tracks new publications as the field evolves.
- Potentially develop a lightweight **research prototype** that implements a baseline method for educational purposes.

---

## Citation

If you find this survey useful, please consider citing:

```bibtex
@article{few_view_xray_ct_survey_2025,
  title   = {From X-ray to CT: A Comprehensive Survey of 2D-to-3D Reconstruction Methods From Classical Statistical Shape Models to Generative and Neural Implicit Frameworks},
  author  = {Sheetal Lodhi},
  year    = {2026},
  note    = {Manuscript under preparation}
}
```
---

## Acknowledgements

We thank the authors of all surveyed works for making their research publicly available. This survey was conducted as part of an academic research project.
