# CI_shiny_presentation
It was the presentation on 05.01.17 at Chemnitz.
The slides were made by rmarkdown.

There were two errors when I render the pdf even having LaTex on OS X.
Solutions have been discussed on the web.

(1) cannot find pdflatex
http://stackoverflow.com/questions/22081991/rmarkdown-pandoc-pdflatex-not-found

Sol:
Add symbolic link to `/Library/TeX/texbin`

`ln -s /Library/TeX/Distributions/.DefaultTeX/Contents/Programs/texbin /Library/TeX/texbin`
check if `/Library/Tex/texbin` is in `$PATH`

(2) pandoc document conversion failed with error 41
https://github.com/rstudio/shiny-examples/issues/34

Sol:
Add the path into `$PATH` in R environment

Use `Sys.setenv(PATH = "original_one + new_symbolic_link")`

`Sys.setenv(PATH=paste(Sys.getenv()['PATH'], "/Library/Tex/texbin", sep = ':'))`
