.PHONY: all viewpdf pdf topdf silent basic latex bibtex full html

NAME=main

all: full topdf

full:
	latex ${NAME}.tex
	latex ${NAME}.tex
	latex ${NAME}.tex
	bibtex ${NAME}
	latex ${NAME}
	latex ${NAME}
	latex ${NAME}

latex:
	latex ${NAME}.tex
bibtex:
	bibtex ${NAME}.tex
basic:
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
	bibtex ${NAME}
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
	pslatex ${NAME}.tex
topdf:
	dvipdf ${NAME}.dvi ${NAME}.pdf

viewpdf:
	@open ${NAME}.pdf

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


pdf: silent viewpdf

.PHONY: clean
clean:
	rm *.toc *.bbl *.blg *.aux *.log *.pdf *.dvi

# vim: sts=8 ts=8 noet ai
