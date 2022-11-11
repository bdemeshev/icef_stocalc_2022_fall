# makefile: tex -> pdf using xelatex

file_name = ha

$(file_name).pdf: $(file_name).tex
	# protection against biber error
	# http://tex.stackexchange.com/questions/140814/
	rm -rf `biber --cache`

	# create pdf
	# will automatically run pdflatex/biber if necessary
	latexmk -xelatex $(file_name).tex

	# clean auxillary files
	latexmk -c $(file_name).tex

# $(file_name).tex : $(file_name).Rnw
# 	Rscript -e "library(knitr); knit('$(file_name).Rnw')"

clean:
	-rm $(file_name).pdf 
	-rm $(file_name).aux 
	-rm $(file_name).log 
	-rm $(file_name).fls 
	-rm $(file_name).out 
	-rm $(file_name).toc 
	-rm $(file_name).synctex.gz
	-rm $(file_name).xdv
	-rm $(file_name).fdb_latexmk
