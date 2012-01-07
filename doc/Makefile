# vim: set ts=8 sts=8 sw=8 noet ai:

# Name of the main latex file which includes others
NAME=main

# Default target
.PHONY: all
all: full topdf

# This compiles fully the document
.PHONY: full
full:
	latex ${NAME}.tex
	latex ${NAME}.tex
	latex ${NAME}.tex
	bibtex ${NAME}
	latex ${NAME}
	latex ${NAME}
	latex ${NAME}

# latex only compiles once
.PHONY: latex
latex:
	latex ${NAME}.tex

# calls bibtex once
.PHONY: bibtex
bibtex:
	bibtex ${NAME}.tex

# Using pslatex instead of latex, same as target 'full'
.PHONY: basic
basic:
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
	bibtex ${NAME}
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex

# Converts the DVI to PDF
.PHONY: topdf
topdf:
	dvipdf ${NAME}.dvi ${NAME}.pdf

# Opens the pdf by the 'open' command, whatever it is
.PHONY: viewpdf
viewpdf:
	@open ${NAME}.pdf

# Same as 'basic' and 'topdf' w/o output
.PHONY: silent
silent:
	@pslatex ${NAME}.tex >/dev/null 2>&1 
	@pslatex ${NAME}.tex >/dev/null 2>&1 
	@pslatex ${NAME}.tex >/dev/null 2>&1 
	@bibtex ${NAME} >/dev/null 2>&1 
	@pslatex ${NAME}.tex >/dev/null 2>&1 
	@pslatex ${NAME}.tex >/dev/null 2>&1 
	@pslatex ${NAME}.tex >/dev/null 2>&1 
	@dvipdf ${NAME}.dvi ${NAME}.pdf

elolap.dvi:
	pslatex elolap.tex

elolap.pdf: elolap.dvi elolap.tex
	@dvipdf elolap.dvi


# Viewing the pdf w/o output
.PHONY: pdf
pdf: silent viewpdf

.PHONY: clean
clean:
	rm *.toc *.bbl *.blg *.aux *.log *.pdf *.dvi
