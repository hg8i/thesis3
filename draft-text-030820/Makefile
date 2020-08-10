
postUrl:=http://www.hg8i.com/thesisPageCount/?pass=4&pageupdate=

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
	# Post thesis length to website!
	pdfinfo thesis.pdf | grep Pages | awk '{print "http://www.hg8i.com/thesisPageCount/?pass=4&pageupdate=" $$2}' | xargs curl --silent --output /dev/null $$1

	# ==================================================
	# Finished:
	# * pdflatex
	# * bibtex
	# * Post thesis length to http://www.hg8i.com/thesisPageCount
	# ==================================================


clean:
	-rm *.dvi *.toc *.aux *.log *.out \
		*.bbl *.blg *.brf *.bcf *-blx.bib *.run.xml \
		*.cb *.ind *.idx *.ilg *.inx \
		*.synctex.gz *~ *.fls *.fdb_latexmk .*.lb spellTmp



