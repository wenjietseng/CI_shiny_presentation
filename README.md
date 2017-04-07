# CI_shiny_presentation
It the presentation on 05.01.17 at Chemnitz.
The slides made by rmarkdown.

There were two errors when I render the pdf even having LaTex on OSX.
Solutions have been discussed on the web.

(1) cannot find pdflatex
http://stackoverflow.com/questions/22081991/rmarkdown-pandoc-pdflatex-not-found

Sol:
Add symbolic link to `/Library/TeX/textbin`

`ln -s /Library/TeX/Distributions/.DefaultTeX/Contents/Programs/texbin /Library/TeX/textbin`
check if `/Library/Tex/textbin` is in `$PATH`

(2) pandoc document conversion failed with error 41
https://github.com/rstudio/shiny-examples/issues/34

Sol:
Add the path into `$PATH` in R environment

Use `Sys.setenv(PATH = "original_one + new_symbolic_link")`

`Sys.setenv(PATH=paste(Sys.getenv()['PATH'], "/Library/Tex/textbin", sep = ':'))`
