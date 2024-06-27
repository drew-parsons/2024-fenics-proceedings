BOOK = book.tex
BOOK.pdf = $(BOOK:%.tex=%.pdf)
BOOK.idx = $(BOOK:%.tex=%.idx)
BOOK.aux = $(BOOK:%.tex=%.aux)
BIB = bibliography.bib

CHAPTERDIR = chapters
PDFLATEX = pdflatex -interaction scrollmode -file-line-error -halt-on-error -synctex=1
BIBTEX = bibtex
MAKEINDEX = makeindex -s svind.ist


all: pdf

pdf: $(BOOK)	
	$(PDFLATEX) $(BOOK)
	for chapterdir in $(CHAPTERDIR)/* ; do \
        $(BIBTEX) $${chapterdir}/main.aux ; \
    done
	$(MAKEINDEX) $(BOOK.idx)
	$(PDFLATEX) $(BOOK)
	$(PDFLATEX) $(BOOK)

