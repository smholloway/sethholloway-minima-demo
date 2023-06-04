---
layout: post
title: ! 'Working with LaTeX: See all your citations'
alias: /blog/2009/07/09/working-with-latex-see-all-your-citations/
categories:
- academics
tags:
- bibtex
- citations
- latex
- regex
- script
- shell
- sources
- tool
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
<span style="text-decoration: underline;">UPDATE</span>

J.P. Knight left a much easier solution in the comments. If you want to see all of your citations the easy way, simply put the \nocite{*} command into your latex file as seen below.
<blockquote>\documentclass[11pt]{report}
\usepackage{natbib}
\bibpunct{(}{)}{;}{a}{,}{,}
\begin{document}
\bibliographystyle{apalike}
\nocite{*}
\bibliography{proposal}    %% your bib file name here
\end{document}</blockquote>
<div>Thanks J.P!</div>
<div></div>
<div><span style="text-decoration: underline;">ORIGINAL</span></div>
I'm currently writing my dissertation (technically my proposal) in <a title="LaTeX Official Page" href="http://www.latex-project.org/">LaTeX</a> (think Microsoft Word without the WYSIWYG interface). As I'm searching for citations, I am overwhelmed at the number of sources in my bibtex file. Rather than staring at the bland, perhaps bloated, syntax with curly braces, spaces, and commas, I created a little script that would let me see how the citations will look in the paper--in a nice PDF bibliography. Here, I present seeAllCitations.sh which takes in your bibtex file as an argument and creates a file with all of your potential citations. After the script completes, just "compile" the file as you normally would and open the resulting pdf/dvi.
<blockquote>#!/bin/sh

# Check input for one argument
if [ $# -ne 1 ]; then
echo "Please input your .bib file as an argument"
echo "Example: ./seeAllCitations.sh proposal.bib"
exit 1
fi

#  Create the file
echo "Creating seeAllCitations.tex that will allow you to see all citations."

# Create a simple tex file that will include citations
echo "\documentclass[11pt]{report}
\usepackage{cite}
\usepackage{url}
\\\begin{document}
\n
All citations from $1 shown below
\n
%% Begin citations" &gt; seeCitations.tex

cat $1 |grep @ |sed s/^@.*{/\\\\\\cite{/ |sed s/,.*$/}\\\\\\\\/ &gt;&gt; seeCitations.tex

echo "%% End citations
\n
\\\bibliographystyle{abbrv}
\\\bibliography{$1}
\n
\\\end{document}" &gt;&gt; seeCitations.tex

# Process completed
echo "Process completed. Enjoy!"
echo "Confused about what to do next? Create the document. For example:
pdflatex seeCitations.tex
bibtex seeCitations.tex
pdflatex seeCitations.tex
open seeCitations.pdf"
exit 0</blockquote>
See any mistakes? Was that at all helpful? Do you have a different (read: better) method for checking your citations?
