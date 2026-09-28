# arXiv Templates

Two LaTeX templates for research preprints: **arXiv Single Column** and
**arXiv Double Column**. Both use the same Libertine typography, mathematical
fonts, centered title, and numbered author affiliations.

| Template | Body | Title, authors, and abstract | Download |
| --- | --- | --- | --- |
| [arXiv Single Column](arxiv-single-column/) | One column | Full width | [ZIP](downloads/arxiv-single-column.zip) |
| [arXiv Double Column](arxiv-double-column/) | Two columns | Full width | [ZIP](downloads/arxiv-double-column.zip) |

## Quick start

Download either ZIP and extract it, or clone the repository:

```sh
git clone https://github.com/LanLanLan-Ian/arxiv_template.git
cd arxiv_template/arxiv-single-column
latexmk -pdf main.tex
```

For the double-column version, build from `arxiv-double-column` instead.
Each folder is self-contained and includes its style, section files, references,
and license. Use a complete TeX Live or MacTeX installation with pdfLaTeX and
BibTeX. The output is `main.pdf`.

## Make it your own

- **Title and authors:** edit `main.tex`, including the PDF metadata commands.
- **Content:** replace the examples in `sections/`.
- **References:** add unique citation keys to `references.bib`.
- **Figures:** add files to `figures/`; examples are in `sections/experiments.tex`.
- **Packages and commands:** edit `preamble.tex`.
- **Typography:** both versions ship with the same `arxiv-style.sty`.

The default body size is 10pt. For larger text use
`\documentclass[11pt]{article}` in the single-column version or
`\documentclass[twocolumn,11pt]{article}` in the double-column version.
The `12pt` option is also supported. Recheck line breaks and floats after changes.

## Double-column layout

The title, author block, and abstract span the page. The introduction,
remaining sections, references, and appendix use two columns separated by a
0.25-inch gutter. The font family, default font size, page size, title styling,
and citation format match the single-column version.

Use `\linewidth` for column-sized figures and tables, and `figure*` or `table*`
for full-width floats. Wide floats normally appear at the top of a later page.
The included table uses `tabularx` so it fits either layout without scaling text.

## Repository structure

```text
arxiv-single-column/     Standalone single-column project
arxiv-double-column/     Standalone double-column project
downloads/              Ready-to-use source archives
.github/workflows/      Automated LaTeX compilation
LICENSE                 Apache License 2.0
```

## Build checks

The GitHub Actions workflow compiles both example manuscripts with pdfLaTeX and
BibTeX. Each run uploads its PDFs as workflow artifacts. Check the latest run in
[Actions](https://github.com/LanLanLan-Ian/arxiv_template/actions) for build status
and output files.

To build locally without latexmk:

```sh
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

The downloadable source archives should be regenerated whenever a template is
changed. They contain the files in the corresponding template folder, with
`main.tex` at the archive root and no generated build files.

## Contributing

For a bug report, include a minimal example, compiler version, and relevant log
output. Include before-and-after screenshots for layout changes. Keep font and
title settings consistent across the two variants unless a difference is intentional.

## License

This repository uses the [Apache License 2.0](LICENSE). LaTeX packages and fonts
retain their own licenses and are installed through your TeX distribution.
Using this template does not change the ownership or license of your manuscript.
This project is an independent preprint style, not an official arXiv template.
