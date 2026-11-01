.PHONY: all clean

all: elteikthesis_en.pdf

elteikthesis_en.pdf: elteikthesis_en.tex titlepage.tex elteikthesis.cls elteikthesis.bib $(wildcard chapters/*.tex) $(wildcard ../images/*)
	latexmk -pdf -interaction=nonstopmode -halt-on-error elteikthesis_en.tex

clean:
	latexmk -c elteikthesis_en.tex
