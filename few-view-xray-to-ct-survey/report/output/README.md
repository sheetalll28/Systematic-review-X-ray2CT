# Survey Output Directory

> This directory contains the fully compiled survey manuscript.

## Available Output

- **`CV_REPORT.pdf`** — The complete survey paper in PDF format.

## Regeneration

If you modify the LaTeX source in `report/`, you can regenerate the PDF using the following commands:

```bash
cd report/
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
mv main.pdf output/CV_REPORT.pdf
```

---

*Status: Survey successfully compiled.*
