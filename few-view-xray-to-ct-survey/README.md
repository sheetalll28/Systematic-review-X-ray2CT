# A Systematic Review of Few-View X-Ray-to-CT Reconstruction: From Single-View Learning to Diffusion-Based 3D Generation

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
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
│   ├── main.tex               ← Master document (includes all sections)
│   ├── references.bib         ← BibTeX bibliography
│   ├── sections/              ← Individual section files
│   │   ├── abstract.tex
│   │   ├── introduction.tex
│   │   ├── methodology.tex
│   │   ├── taxonomy.tex
│   │   ├── gan_methods.tex
│   │   ├── transformer_methods.tex
│   │   ├── neural_field_methods.tex
│   │   ├── diffusion_methods.tex
│   │   ├── datasets_and_domain_gap.tex
│   │   ├── comparative_analysis.tex
│   │   ├── future_directions.tex
│   │   └── conclusion.tex
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
├── tables/                    ← CSV templates for comparison tables
│   ├── comparison_table_template.csv
│   └── paper_summary_template.csv
│
├── figures/                   ← Placeholder directory for figures
│   ├── README.md
│   ├── taxonomy_placeholder.txt
│   └── method_timeline_placeholder.txt
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

### 1. Browse the Survey Content

- Start with [`report/main.tex`](report/main.tex) to view the manuscript structure.
- Individual sections are in [`report/sections/`](report/sections/).
- References are managed in [`report/references.bib`](report/references.bib).

### 2. Explore the Paper Metadata

- [`paper_metadata/included_papers.md`](paper_metadata/included_papers.md) explains the paper categorization scheme.
- Core, supporting, and background papers are listed in their respective files.

### 3. Compile the LaTeX Report

```bash
cd report/
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Or use an editor such as Overleaf, TeXstudio, or VS Code with the LaTeX Workshop extension.

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
