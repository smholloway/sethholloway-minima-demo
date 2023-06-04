---
layout: post
title: Choosing the right library for your Java project
alias: /blog/2011/09/30/choosing-the-right-library-for-your-java-project/
categories:
- technical
tags:
- java
- libraries
- reuse
- software
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Software libraries can tremendously help software development. At best, the libraries are well tested pieces of functionality that integrate easily into your project and prevent you from re-inventing the wheel. On the negative side, third-party libraries could add to your costs or prevent your company from being sold, they could be confusing and poorly documented, or they could work unexpectedly. I've used a number of libraries in the past (Ruby and Ruby on Rails push libraries heavily; in Java I like jsoup and log4j), but I was curious how pros chose so I asked around and searched a bit.

You can read the <a title="Reddit: Handy Java Libraries" href="http://www.reddit.com/r/java/comments/kis7l/handy_java_libraries_you_use">Reddit take on handy Java libraries</a>.

And here's advice from Lane:
<blockquote>I'd focus on these:

Normal coding
Apache Commons: <a href="http://commons.apache.org/" target="_blank">http://commons.apache.org/</a>
Guava: <a href="http://code.google.com/p/guava-libraries/" target="_blank">http://code.google.com/p/<wbr>guava-libraries/</wbr></a>
Jackson JSON parser: <a href="http://jackson.codehaus.org/" target="_blank">http://jackson.codehaus.org/</a>
Spring: <a href="http://www.springsource.org/" target="_blank">http://www.springsource.org/</a>
ActiveMQ

Unit Testing:
jUnit4
Hamcrest matchers
Mockito (I absolutely dislike mocking tho)

When it comes to libraries try to find ones that have a lot of current activity.

The best code is the code you don't have to write.  So I try to write
as little as possible.</blockquote>
And Drew:
<blockquote>
<div>Here are a couple considerations off the top of my head, but by no means are these exhaustive nor complete...</div>
<div>Quick summary - Choosing to use a library should be economics driven.  Look at ROI.  Yes, for an engineer, the excitement of using the newest cool tool is a positive return, but only one of many 10's of terms in the equation... and probably not one of the larger terms.</div>
<div>0) Documentation - Any library (or application) worth your time should have decent documentation.  It's hard to recognize good documentation for new engineers, so beware things recommends by "kids".  There are basically two camps on the documentation side... the big book (e.g. maven) and the mailing list (e.g. guava).  The big book is pretty obvious.  Guava's documentation is a collection of power-point presentations and a very active tag on stack-overflow.  Personally, I prefer Guava's documentation over the big-book style.</div>
<div>1) Maturity of library - Steer clear of anything that is a prototype, a "place to test advanced features", etc.  It's not worth your time to rewrite your code when the api changes.</div>
<div>2) Maturity of release - Steer clear of anything X.0.0.  It's broken and you'll have to upgrade soon... another time suck.  Given the choice between 3.5.2 and 4.0.0, always go with 3.x.</div>
<div>3) Client list - You're looking for things that are used by other big projects.  slf4j does a good job of this... it's a mid-aged library but they have a impressive list of projects that use the library right on the home page.  This is a good sign.</div>
<div>4) Consider proprietary libraries - Sometimes it makes a lot of sense to just buy it.  The price for these libraries is always stunning, but you need to consider ROI, not cost.  Your ROI calculation needs to include design, implementation, maintenance, time-to-market, and how pissed your customer will be if you got something wrong.  Odds are very good that a proprietary library has already gotten that thing wrong and is amortizing the cost.</div>
<div>Plus, it's nice to have someone to call that has to answer your question.  No one has to answer your guava question (and there are a number of unanswered questions on SO).  I may sound strange, but it's fantastic to get a reply from a vendor in a hour that says "I understand your question, but we don't do that right now."  You can then move on and never second guess that decision.</div>
<div>5) Legal - Never use anything that is GPL or LGPL only.  Apache, CDDL, BSD, and others are ok.  Most decent libraries are dual licensed.  Figure out which licenses are 'ok' for yourself, don't take my word for it.  Here's the reason... at some point you might want to sell your idea/company to someone else.  If you have GPL libraries in your code base, it's gonna cost you real money when you sell, and real time when you have to extract it after the sale.  I know you can use a GPL library and be safe... but it's just too scary for people who might want to buy you later.  Now that's not to say you can't use GPL libraries to build your product.  We all have one or two GPL tools that we use... but they don't get rolled into the final product (e.g. findbugs).</div>
<div>6) Generics - A sub-item for maturity probably, but a specific item to watch for.  If a library doesn't use generics at all, it's a red flag.  There are cases where it doesn't make sense to accept types from the application, so the library doesn't need generics... but this is pretty rare.  I would expect that a library would return at least one collection... and if that collection is untyped, it's a flag that something is up.  (It could be backwards compatibility, unmaintained code, or authors that don't "get it", or something else)</div>
<div>7) Standards - Not so much.  I used to look for libraries that conformed to standards.  I don't find that to be a big deal anymore.  If a library is worth its salt, it's documented either via some standard or by itself.  (Tomcat and Jetty conform to standards wich is great.  Guava is non-standard, but I don't care).</div>
<div>8) Beware libraries that have lots of dependencies.  Sometimes it's unavoidable, but try to avoid them if possible.  They make the final product bigger (not a huge deal), they need more updates (again, you can avoid this most of the time), but the big one is library clashing. You don't want to include a nice stable library X.jar that depends on a library Y.jar in 2010, then find out that you really would like to use the newest version of Y.jar directly, but it's got a new API.  You may be able to upgrade X.jar to use the new Y.jar, but you'll also be upgrading all the other libraries it depends on too.  Basically, library dependencies are not a tree, they're a directed graph (acyclic if you're lucky).  The bigger and more connected that graph is, the more problems that it can cause in the build system.</div>
<div>Summary) Basically, you should always be looking at ROI.  There's just no way to compute the actual ROI, so you have to use your experience to make an approximation.  If two or three choices are about the same, then try to make a case for one of them in an email to yourself (or your boss).  See how easy it is to write up an argument to convince someone else.</div></blockquote>
Who replied later with more information:
<blockquote>
<div>I thought about it a little more today, and if I was going to write up a real article for the web, I might propose a ROI formula with a half-dozen terms... then describe how to evaluate a library for each term.  If I was lucky, I could pick terms that were really independent of each other.</div>
<div>Something like "cost to design + cost to build + cost to maintain &gt;? dollar cost for license + cost to integrate + (prob. of update)*(cost to apply update) + ..."</div></blockquote>
Excellent advice! Thanks to Drew and Lane!

I'm interested in other opinions. How do you choose a library? Which do you use most frequently? Have any horror stories derived from code reuse?
