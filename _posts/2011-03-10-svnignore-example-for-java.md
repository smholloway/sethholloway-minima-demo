---
layout: post
title: .svnignore Example for Java
alias: /blog/2011/03/10/svnignore-example-for-java/
categories:
- technical
tags:
- example
- ignore
- java
- subversion
- svn
- version control
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
.svnignore is my attempt to create the equivalent of .gitignore. After creating the file I had to set the svn:ignore property before it worked:
<code>svn propset svn:ignore -F .svnignore .</code>

First, a little background: my PhD work uses <a title="Sun SPOT World" href="http://www.sunspotworld.com/">Sun (Oracle) SPOT devices</a> that run the <a title="Squawk VM" href="http://www.research.sun.com/projects/squawk/index.html">Java Squawk VM</a> (kinda like <a title="Wikipedia: Java Micro Edition" href="http://en.wikipedia.org/wiki/Java_Platform,_Micro_Edition">Java ME</a>). For version control, we use <a title="Subversion" href="http://subversion.tigris.org/">Subversion</a>. In keeping with good version control practices, I want to avoid putting binary and compiled files into version control. The easiest way to do this is a solid .svnignore file. I spent a few minutes trying to find a .svnignore example for Java and could not find anything, so I built one myself based on several examples I saw.

.svnignore
<blockquote>
    *.class
    build/*
    j2meclasses/*
    .classpath
    .project
    .settings
    *.war
    *~
    *.lock
    *.DS_Store
    *.swp
    *.out
    *.bak
    *.tmp
    *.log
    log*.txt
    .idea
    .git
</blockquote>
From the top, ignore class files, the build directory, the classes directory, our local classpath/project/settings, the compiled deployment package (WAR/JAR), any tilde backup files, a OS X specific directory,  VI files that are being edited, log files, backup and temporary files, IDE files (thanks <a title="Lane Holloway is awesome" href="http://www.laneholloway.com/">Lane</a>), and finally any git files (this part could be expanded to include other version control systems like Bazaar or Mercurial).

If I missed something, please let me know.

**UPDATE**

GitHub has published a list of .gitignore files for a number of languages: <a title="GitHub's gitignore files" href="https://github.com/github/gitignore">https://github.com/github/gitignore</a>. You can pop these into your .svnignore and apply the properties.


