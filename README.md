#FP7 LaTeX Template

After a long search around the web, it seems that no LaTeX template could be found for FP7. The only LaTeX class found is [eurpoposal.cls](http://www.ctan.org/pkg/euproposal), but it seems deprecated and do not feet anymore the official Rich Text Format (OMG) template. So i made it myself!

## Usage

As I am not a LaTeX guru, i just made a .tex template file. Nevertheless, I just need to precize a few points about this template distribution.

### XeLaTeX

It uses [XeLaTeX](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=xetex) to call system fonts instead of LaTeX embedded ones. If the [ubuntu font family](http://font.ubuntu.com/) is not installed on your system, you can use the whatever-font-you-want ( see: [this wikipedia reference](http://en.wikipedia.org/wiki/TrueType) by changing the following lines (5 to 7) in the .tex preamble:

	% -- Fonts (XeLaTeX)
	\usepackage{fontspec} %for loading fonts
	\usepackage{xunicode,xltxtra}
	\defaultfontfeatures{Mapping=tex-text}
	\setmainfont{Ubuntu}
	\setsansfont{Ubuntu}
	\setmonofont{Ubuntu}

### Makefile-latex

To compile the proposal latex source, I recently discovered the [latex-makefile project](http://code.google.com/p/latex-makefile/) and integrated it. By default, latex-makefile uses latex to compile. To use xelatex, create a Makefile.ini with the following line:

	BUILD_STRATEGY:=xelatex
	
And then to compile, simply type:

	prompt@bash:~ $ make

This will generate a PDF file of your proposal. And to clean up your directory with messy auxiliary files, type:
	
	prompt@bash:~ $ make clean

