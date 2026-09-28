# arXiv Double Column

A standalone LaTeX template for research preprints, using Libertine text,
matching mathematics, a centered title, and numbered author affiliations.

## Layout

- Two-column body with a 0.25-inch gutter.
- Full-width title, authors, and abstract.
- Standard `article` title styling and 10pt body text by default.
- US Letter paper, with a 6.8-inch text width and 9-inch text height.
- No conference header, review line numbers, or email line by default.
- No first-line indentation in the abstract.

## Build

Use a complete TeX Live or MacTeX installation with pdfLaTeX and BibTeX:

```sh
latexmk -pdf main.tex
```

Or run `pdflatex main.tex`, `bibtex main`, and `pdflatex main.tex` twice.
The output is `main.pdf`. Clean auxiliary files with `latexmk -c`.

## Edit your manuscript

1. Set `PaperTitle`, `PaperAuthors`, the author list, and affiliations in `main.tex`.
2. Replace the examples in `sections/`. The abstract file contains text only.
3. Add uniquely keyed references to `references.bib`.
4. Store figures in `figures/` and add manuscript-specific commands to `preamble.tex`.

The `arxiv-style.sty` file supplies the same fonts and title configuration as the
other layout. It is included here, so this folder can be used independently.
Use `\citet{key}` for narrative citations and `\citep{key}` for parenthetical
citations. The template uses `plainnat` and BibTeX, not Biber.

## Font size

Change the first line of `main.tex` to
`\documentclass[twocolumn,11pt]{article}` for 11pt text,
or substitute `12pt`. This also adjusts relative font sizes and pagination.
Keep the `twocolumn` option when changing the font size.

## Figures and tables

Use `\linewidth` to size an image or table to its current column.
Use `figure*` or `table*` for a float spanning both columns. The title and abstract use the documented `abstract` package workflow: `twocolumn`, `onecolabstract`, and `saythanks`. Keep that block intact.
The sample table uses `tabularx` so its text can wrap within the available width.

## License

Apache License 2.0; see [LICENSE](LICENSE). Dependencies retain their own licenses.
Your manuscript content remains yours. This is an independent preprint template,
not an official arXiv template.
