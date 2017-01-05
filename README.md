# CI_shiny_presentation
It the presentation on 05.01.17 at Chemnitz.
The slides made by rmarkdown.

There were two errors when I render the pdf even having LaTex on OSX.
Solutions have been discussed on the web.
1. cannot find pdflatex
http://stackoverflow.com/questions/22081991/rmarkdown-pandoc-pdflatex-not-found

2. pandoc document conversion failed with error 41
https://github.com/rstudio/shiny-examples/issues/34
Just add the symbolic link `/Library/TeX/texbin`
into `Sys.setenv(PATH = "original_one_and_symbolic_link")`
