# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository contains LaTeX example templates and documents demonstrating various LaTeX features and packages. It serves as a reference collection for mathematical proofs, colored boxes (tcolorbox), process diagrams, and academic article formatting.

## Building Documents

Compile LaTeX files to PDF using:

```bash
pdflatex <filename>.tex
```

For documents with bibliographies (like `example_proof_article/example_proof_article.tex`):

```bash
pdflatex <filename>.tex
bibtex <filename>
pdflatex <filename>.tex
pdflatex <filename>.tex
```

Note: LaTeX typically requires multiple compilation passes to resolve cross-references, citations, and table of contents.

## Repository Structure

The repository is organized into template categories:

- **`tcolorbox_examples/`**: Advanced colored box examples using tcolorbox package
- **`example_proof_article/`**: Complete academic article template with proofs and bibliography
- **`math_proofs/`**: Mathematical theorem and proof templates using amsthm
- **`tex_processes/`**: Process documentation template with TikZ flowcharts

## Key LaTeX Packages Used

### tcolorbox (`tcolorbox_examples/box.tex`)
Demonstrates advanced colored box features including:
- Basic colored boxes with titles and two-part boxes (`\tcblower`)
- Code listings with syntax highlighting (`tcblisting`)
- Custom theorem environments (`\newtcbtheorem`)
- Breakable boxes for multi-page content
- Watermarks and nested boxes
- File generation (`savelowerto`) - generates `box_ex.tex` during compilation

### Mathematical Proofs (`math_proofs/proofs.tex`)
Template for formal mathematical documents with:
- Custom theorem environments: `theorem`, `lemma`, `problem`, `exercise`, `reflection`, `proposition`, `corollary`, `axiom`
- Standard math number set commands: `\N`, `\Z`, `\Q`, `\R`, `\C`, `\I`
- Custom header setup using fancyhdr
- Automatic theorem listing with `\listoftheorems`

### Process Documentation (`tex_processes/process.tex`)
Template for operational procedures with:
- TikZ flowchart shapes: startstop, io (trapezium), process (rectangle), decision (diamond)
- Margin notes using `marginnote` package
- Highlighted boxes using tcolorbox
- Asymmetric page layout (2.5cm left, 5cm right margin for notes)

## Important Notes

### Generated Files
Running `pdflatex tcolorbox_examples/box.tex` generates `tcolorbox_examples/box_ex.tex` as a demonstration of the `savelowerto` feature. This file is automatically created, should not be manually edited, and is gitignored.

### PDF Output
All generated PDF files are gitignored. Always compile from source `.tex` files.

## Common Modifications

When creating new documents based on these templates:

1. **For mathematical proofs**: Use `math_proofs/proofs.tex` - update author in `\chead{}` and customize available theorem environments
2. **For colored presentations**: Use `tcolorbox_examples/box.tex` - requires tcolorbox package with `[most]` option
3. **For process documentation**: Use `tex_processes/process.tex` - requires tikz with shapes, arrows.meta, and arrows libraries
4. **For academic articles**: Use `example_proof_article/example_proof_article.tex` - includes bibliography support

## Bibliography Management

Documents using citations require:
1. `\usepackage{...}` for bibliography packages (already included in relevant templates)
2. `\begin{thebibliography}{9}` environment with `\bibitem` entries
3. Multiple pdflatex runs to resolve citations
