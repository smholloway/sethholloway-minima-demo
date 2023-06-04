---
layout: post
title: New Software Metrics
alias: /blog/2012/07/24/new-software-metrics/
categories:
- technical
tags:
- metrics
- programming
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I just completed the <a title="2012 State of Clojure survey" href="http://cemerick.com/2012/07/19/2012-state-of-clojure-survey/">2012 State of Clojure survey</a> and it got me thinking about how to fairly judge languages like Clojure. We need new software metrics. Performance is easy to quantify: write a program, run it a lot, and measure the time it took. Do that across multiple languages, and you can find a winner (the one offering the most operations per time). For example, check <a title="Debian Language Shootout" href="http://shootout.alioth.debian.org/">Debian's Language Shootout</a> where Fortran and C rule. However, solely measuring performance misses a bigger (in my opinion) problem: development speed and ease-of-use. In my limited experience, Clojure is significantly shorter and easier to reason about that equivalent C projects. To be fair, it's been a while since I wrote much in C, but Clojure has also been easier to understand and change than Java code. In addition, Clojure programs are (basically) concurrent out-of-the-box. I think concurrency is generally very difficult and error-prone; however, concurrency is increasingly necessary--making Clojure that much stronger. But none of that is captured in common metrics.

<img class="alignleft" style="margin-right: 30px;" title="Software Metrics book cover" src="http://ourcraft.files.wordpress.com/2009/08/software-metrics-cover-scan.jpg" alt="Software Metrics book cover" width="59" height="89" />
With the availability of lots of developers online I think we could tackle harder to quantify metrics like

 * performance per line of code
 * performance per development time
 * performance per noob minute
 * comprehensibility per time
 * time to change a line of code

The first pass on how to achieve this (tons of issues, no doubt): survey all the developers you can find. Collect all the information you can through the survey and GitHub tie-ins then ask people to perform tasks like explaining a piece of code and writing/changing programs across languages. An automated approach might start by finding a series of program solutions (from a set like <a title="99 Bottles of Beer" href="http://99-bottles-of-beer.net/">99 Bottles of Beer</a>, <a title="Project Euler Problems" href="http://projecteuler.net/problems">Project Euler</a>, <a title="Rosetta Code" href="http://rosettacode.org/wiki/Rosetta_Code">Rosetta Code</a>, or <a title="99 Problems in Scala" href="http://99problemsinscala.wordpress.com/">99 Problems in X</a>), then gather data about each solution and people's feelings about each. Maybe you could seed a bug and see how long it takes people to find and fix the bug.

Have I missed better software metrics? What metrics define a language you want to write in?  How can we accurately collect those metrics?
