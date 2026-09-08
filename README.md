# LaTeX Resume

This repository contains two resume variants that share one set of formatting and section content.  

  As a current computer science student with prior production software engineering experience at Amazon Ads, my background is relevant to both
  internship and full-time opportunities. The internship resume foregrounds my education and current student status, while the full-time resume
  foregrounds my professional engineering experience. Both variants represent the same background, with their organization tailored to the
  role.

## Published resume

The internship-focused resume is the canonical public version:

**[View current resume](docs/Resume.pdf)**

GitHub Actions rebuilds that file after each push. The full-time variant is built by the same workflow and uploaded as a downloadable workflow artifact, but it is not committed into `docs/`.

## Project structure

```text
resumes/
  internship.tex       Public, education-first resume
  full-time.tex        Experience-first application variant
shared/
  resume-format.tex    LaTeX preamble, layout, and reusable commands
  sections/            Shared resume content
docs/
  Resume.pdf           Canonical public PDF
build/                 Local generated PDFs (ignored by Git)
```

`resume.tex` remains as a compatibility entry point for the public internship resume.

## Prerequisites

On Windows, install [MiKTeX](https://miktex.org/download) and allow it to install missing packages automatically. Restart the terminal after installation.

## Build locally

Run these commands from the repository root:

Create the build directory; only necessary the first time:
```powershell
New-Item -ItemType Directory -Path build -Force | Out-Null
```
Build the internship resume:
```powershell
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=build resumes/internship.tex
```
Build the full-time resume:

```powershell
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=build resumes/full-time.tex
```

Open either generated PDF:

```powershell
Start-Process build/internship.pdf
Start-Process build/full-time.pdf
```

The `build/` directory is ignored by Git. The `.tex` files are the permanent source of truth and can regenerate both PDFs on any machine with LaTeX installed.

## Download the full-time build from GitHub

Open the repository's **Actions** tab, select a successful **Build LaTeX Resumes** run, and download **full-time-resume** from the run's **Artifacts** section.
