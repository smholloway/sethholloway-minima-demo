---
layout: post
title: My LaTeX resume template
alias: /blog/2011/06/24/my-latex-resume-template/
categories:
- personal
tags:
- latex
- resume
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Several years ago I started writing my [resume in LaTeX](https://github.com/smholloway/resume/tree/master/latex). It was a great way to learn LaTeX and have fine-grained control over my resume. Overall, I'm pleased with it, but I must admit that updating and recompiling the file can be a chore. 

I've had several people ask for my LaTeX resume template, so I figured I would share the wealth. You can find my custom resume file, mostly reduced to a template, in the [latex folder of my resume repo on GitHub](https://github.com/smholloway/resume/tree/master/latex).

To generate your resume, download and edit the .tex file, then compile (I use pdflatex on Mac, Windows, and Linux). Et voila! You have a nice looking PDF resume.

**Update** Here's my reply to the question from Yash.
<div>I'm not sure I understand exactly what you want, but I would start by inserting a new contact section</div>
<div></div>
<div><span style="font-family: 'courier new', monospace;">\contact{Yash}{}{}{}</span></div>
<div></div>
<div></div>
<div>You could also create a new contact command, say a contact header. Compared to the standard contact command you remove the centering and trim it down to whatever number of arguments you want. Here's an example for a left-aligned name.</div>
<div></div>
<div><span style="font-family: 'courier new', monospace;">\newcommand{\contactHeader}[1]{</span></div>
<div><span style="font-family: 'courier new', monospace;"> \begin{changemargin}{-0.5in}{-0.5in}</span></div>
<div><span style="font-family: 'courier new', monospace;">    {\Large \scshape {#1}}\\ \smallskip</span></div>
<div><span style="font-family: 'courier new', monospace;"> \end{changemargin}</span></div>
<div>}</div>
<div></div>
<div></div>
<div>To control the spacing, consider forcing a newpage, then inserting the header like so</div>
<div></div>
<div><span style="font-family: 'courier new', monospace;">\newpage </span></div>
<div><span style="font-family: 'courier new', monospace;"> </span></div>
<div><span style="font-family: 'courier new', monospace;">\contactHeader{Yash}).</span></div>
<div></div>
Beyond that, you're on your own! Tinker a bit and see what you come up with.
