# English BSc thesis

Full English translation of `../../szakdolgozat.pdf`, based on
`../elteikthesis_hu.tex` and all four chapters in `../samples_hu/`.

- `elteikthesis_en.tex`: main document and English metadata.
- `chapters/`: translated introduction, user documentation, developer documentation,
  and conclusion, including all captions, tables, and test cases.
- `titlepage.tex`: cover layout adjusted to fit the English text.
- `elteikthesis.bib`: bibliography with the original citation keys and source titles;
  Hungarian publications remain cited in Hungarian.
- `elteikthesis.cls`: unchanged copy of the original ELTE thesis class, including
  its license notice.
- `elteikthesis_en.pdf`: compiled English thesis.

The document reuses the existing illustrations in `../images/`, whose UI labels
and code identifiers are already English. Keep this folder within
`Docs/elteikthesis/` so those relative image paths continue to work.
The chapter structure, figures, equations, citations, and documented test cases
follow the Hungarian source. English decimal notation and English labels are used.

## Build

Requires a LaTeX installation with the packages used by `elteikthesis.cls`,
PDFLaTeX, Biber, and latexmk (for example, TeX Live with the appropriate packages).

From the repository root:

```sh
make -C Docs/elteikthesis/english
```

Or, from this directory:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error elteikthesis_en.tex
```

To build without latexmk, run the following in this directory:

```sh
pdflatex -interaction=nonstopmode -halt-on-error elteikthesis_en.tex
biber elteikthesis_en
pdflatex -interaction=nonstopmode -halt-on-error elteikthesis_en.tex
pdflatex -interaction=nonstopmode -halt-on-error elteikthesis_en.tex
```

`make clean` removes auxiliary build files while retaining the PDF.
