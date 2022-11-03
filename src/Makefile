COMPILE = pdflatex
FLAGS = -pdf -shell-escape

RM = rm -rf

SRC = main.tex \
      intro.tex \
      setup.tex \
      resume.tex \
      $(wildcard task*.tex) \
      $(wildcard assets/*) \
      mydocstyle.sty
OUT = crossplane-taikun-workshop

all: $(OUT).pdf

docker:
	DOCKER_BUILDKIT=1 docker build --rm --target bin --output . .

$(OUT).pdf: $(SRC)
	$(COMPILE) $(FLAGS) -jobname=$(OUT) $<
	$(COMPILE) $(FLAGS) -jobname=$(OUT) $<


clean:
	$(RM) *.dvi *.aux *.log *.nav *.toc *.snm *.out *.pyg _minted* *.fls *.fdb_latexmk *.bcf *.gz

distclean: clean
	$(RM) $(OUT).pdf

.PHONY: clean distclean all docker
