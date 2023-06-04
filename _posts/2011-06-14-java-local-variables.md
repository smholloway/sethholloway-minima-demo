---
layout: post
title: Java local variables
alias: /blog/2011/06/14/java-local-variables/
categories:
- technical
tags:
- effective
- java
- local variables
- programming
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I'm learning a ton this summer as I relearn old tricks and learn new tricks. Among other technologies, frameworks, languages, and techniques, I'm improving my Java skills. A friend recommended <a href="http://www.amazon.com/dp/0321356683/?tag=theven01-20">Joshua Block's Effective Java Version 2</a>. The introduction succinctly states that the book aims to improve your usage of Java--something not usually taught in classes or discussed in book. Here are a few things I (re)learned:

 * Local variables should be instantiated; if you cannot assign a sane default value, you shouldn't be assigning the variable yet.
 * Variables should be located near their use. In the C style you would declare all variables at the top of the method; however, this is not the best practice in modern Java. (Does anyone know if the 'variables at top' still reigns in C?)
 * while loops should be used only if you need the local index variable outside the loop
 * For-each loops should be used whenever possible
 * The next best loop is a for loop with the end condition assigned in the loop (a technique I believe we could weakly call <a title="Wikipedia: memoization" href="http://en.wikipedia.org/wiki/Memoization">memoization</a> because we only have to calculate something once), for example:

    for (int i = 0, len = myDataStructure.calculateSomething(); i &lt; len; i++) {
        // do something
    }

