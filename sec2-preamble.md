 ## Getting Started: Basic Syntax
 
To write in LaTeX code, you have to provide LaTeX with two things: code to *describe* what you want to do, and a "guidebook" to tell LaTeX how to *intepret* what you want to do.

The "guidebooks" are called packages. **TeXLive 2012 comes with all of the packages you'll need for this guide.** However, if you ever want to install packages that don't come with TeXLive, check out [this PDF](http://sachaepskamp.com/wp-content/uploads/2011/10/Install.pdf) for a great walkthrough.
 
 ### the preamble
 
 Every LaTeX file has what's called a preamble. This is where you load all the packages (i.e. the "guidebook") that LaTeX will use to interpret your code.
 
 The LaTeX preamble that comes within "article.tex" looks like this:

<pre><code> 
\documentclass[11pt,article,oneside]{memoir}
\usepackage{kjhmemsty}
\usepackage{mathspec}
\usepackage{fixltx2e}
\usepackage[flushleft]{threeparttable}
\usepackage{rotating}
\usepackage{tabularx}
\usepackage{longtable}
\usepackage{appendix}
\usepackage{wrapfig}
\usepackage{array}
\usepackage{comment}
\usepackage{xunicode}
\usepackage[american]{babel}
\usepackage[babel,autostyle]{csquotes}
\usepackage[authordate,sorting=nyt,backend=biber,maxcitenames=2]{biblatex-chicago}
\addbibresource{/Users/School/Dropbox/Manuscripts/bib/complete.bib} 
\DeclareFieldFormat[article]{title}{\mkbibquote{#1}}
\DeclareFieldFormat[book]{title}{\mkbibemph{#1}\isdot} % for books
\DeclareFieldFormat{booktitle}{\mkbibemph{#1}} % for edited volumes
\setallmainfonts[Mapping=tex-text]{Minion Pro}
</pre></code>

Looks pretty intimidating, right? Don't worry, we're going to walk through what each of the packages means.

    \documentclass[11pt, article,oneside]{memoir}
 
 The document class tells LaTeX what kind of file to expect, and describes very, very basic formatting. In this case, it tells LaTeX to expect an `article` of class `memoir`. The [Memoir](http://www.tex.ac.uk/tex-archive/macros/latex/contrib/memoir/memman.pdf) class is an advanced type of LaTeX document that allows for a lot of customization. Don't worry about that until you have advanced knowledge of LaTeX. The `oneside` command just tells LaTeX to format the document for printing on one side of a page, rather than changing the margins to make room for, say, binding in a book.  `11pt` is the font size, but don't worry about that until later.
 
     \usepackage{kjhmemsty}
 
 The package `kjhmemsty` is a link to my modified version of a style file created by [Kieran Healy](http://www.kieranhealy.org). The original is available [here](https://github.com/kjhealy/latex-custom-kjh). 
 
 ### within the document