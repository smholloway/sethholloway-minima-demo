---
layout: post
title: We need an integrated front-back web programming language
alias: /blog/2011/06/30/we-need-an-integrated-front-back-web-programming-language/
categories:
- Internet
tags:
- css
- database
- html
- integrated
- web programming
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Modern web programming requires a lot of knowledge--too much, I'd say. To write a complete web application you need to work with HTML, CSS, JavaScript, a programming language (PHP, Python, Ruby, Java, etc), and a database. Even if you're a head-down back-end programmer, you should know about the structure and style of the front-end; as a front-end designer, you would do well to understand the framework and database.

There has been a huge explosion of web frameworks radically lowering the barrier to entry for any and all programmers. So, you know C++ and there's a C++ web framework, but you'll still need to know HTML, CSS, and JavaScript on the front-end and a database on the back-end. Node.js is potentially interesting for many reasons, but perhaps the most exciting thing is that you can program the front- and back-end using JavaScript. Better than having to learn JavaScript and a back-end language, but you will still need to know a database, HTML, and CSS.

As I see it, the shortest path would be a high-level programming language with an ORM (object relational mapper) that integrates template builders (something like mokk.me or Dreamweaver). The ORM abstracts out database specifics and allows the programmer to work with a more familiar construct, objects, while providing necessary methods like save, edit and delete. A template builder would visually handle HTML/CSS so that it feels more like design than development. Allowing components to be optimized later (replace or tweak the ORM with better SQL calls) would make the language/framework even better.

An alternative approach is an open source Flash-type language, that benefits from a standard plugin container. Sadly, in over 20 years of the web, the most integrated solution we have is Adobe Flash--a much maligned (insecure, bloated, slow, proprietary, ...) language. For all its faults, Flash allowed people to create dynamic web pages that rendered uniformly--as designed--across browsers. Opening the spec may help as open specs are generally more secure and more optimized than closed versions. If the spec was open, people could write converters from various languages allowing everyone to produce the same output.

While we research an integrated web language there's also room for people to research a new application container. The web browser replacement could use the same stack (TCP/IP, HTTP and HTML) or define new protocols.

Did I miss an option? What do you think will win?
