
default: thesis.tex 
	pdflatex thesis.tex $<
	# ==================================================
	# Finished:
	# * pdflatex
	# (To run bibtex also, "make full")
	# ==================================================

full: thesis.tex 
	pdflatex thesis.tex $<
	-bibtex  $(basename $<)
	pdflatex thesis.tex $<
	pdflatex thesis.tex $<
	# ==================================================
	# Finished:
	# * pdflatex
	# * bibtex
	# ==================================================


clean:
	-rm *.dvi *.toc *.aux *.log *.out \
		*.bbl *.blg *.brf *.bcf *-blx.bib *.run.xml \
		*.cb *.ind *.idx *.ilg *.inx \
		*.synctex.gz *~ *.fls *.fdb_latexmk .*.lb spellTmp


