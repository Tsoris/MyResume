# LaTeX Resume

This repository contains my resume written in LaTeX.

## Prerequisites

### Windows

Install **MiKTeX**:

- https://miktex.org/download

During installation:

- Select **"Install missing packages on the fly"**
- Choose **"Yes"** when prompted to allow automatic package installation
- Use default installation settings

After installation, restart your terminal.

## Build Locally

From the repository root, run:

```bash
pdflatex resume.tex
```

The generated PDF will be written to `resume.pdf`.

## Published PDF

The repo publishes the built resume to `docs/Resume.pdf` through GitHub Actions.
