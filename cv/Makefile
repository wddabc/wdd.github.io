# Dingquan Wang 
# 
# Makefile for LaTeX and Bibtex.  Change the NAME and BIB parameters
# to be the name of the .tex and .bib files respectively.

# Can edit the parameters below to be the relevant filenames.

MAIN=cv
BIB=cv

# All the pdfs in the fig directory.
figures=$(wildcard fig/*.pdf)

all: $(MAIN).pdf

$(MAIN).pdf:$(MAIN).tex $(figures) 
	ln -sf build/$@ .
	latexmk -outdir=build -auxdir=build -pdf -pvc $(MAIN).tex

# Clean up the various extra files created by pdflatex etc.
clean:
	rm -f $(MAIN).aux $(MAIN).bbl $(MAIN).blg $(MAIN).log \
		$(MAIN).rel $(MAIN).toc $(MAIN).synctex.gz \
		$(MAIN).out $(MAIN).pdf \
		$(MAIN).fls $(MAIN).fdb_latexmk \
		$(MAIN).loa $(MAIN).lof $(MAIN).lot \
		 _region_.* *~
	rm -rf auto/
	rm -rf build/

# The phony targets ensure that this will run even if files with
# the same name are accidentally created.
.PHONY: all
.PHONY: clean
.PHONY: clean-biber
.PHONY: serve
