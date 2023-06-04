---
layout: post
title: Highlighting the current page link in a navigation bar template
alias: /blog/2011/06/29/highlighting-the-current-page-link-in-a-navigation-bar-template/
categories:
- Internet
tags:
- css
- html
- jquery
- navigation
- web
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I have not seen anything about how to properly highlight what page you're currently on when using a templated navigation bar on a dynamic webpage... I couldn't even google for a solution because I don't know the correct terminology.

There are a number of ways to highlight the link to the page you're currently on. For example, you could pass a parameter and alter the view based on the parameter; or you could include the navigation pane in each content view then apply the highlight with the page. I don't think either of those solutions is very clean, so here's my solution using HTML, CSS, and jQuery (it should work across browsers).
<pre>&lt;!-- index.html --&gt;</pre>
<pre>&lt;div id="topnav"&gt;</pre>
<pre>	&lt;ul&gt;</pre>
<pre>		&lt;li&gt;&lt;a href="home"&gt;Home&lt;/a&gt;&lt;/li&gt;</pre>
<pre>		&lt;li&gt;&lt;a href="about"&gt;About&lt;/a&gt;&lt;/li&gt;</pre>
<pre>		&lt;li&gt;&lt;a href="links"&gt;Links&lt;/a&gt;&lt;/li&gt;</pre>
<pre>		&lt;li&gt;&lt;a href="services"&gt;Services&lt;/a&gt;&lt;/li&gt;</pre>
<pre>		&lt;li&gt;&lt;a href="contact"&gt;Contact&lt;/a&gt;&lt;/li&gt;</pre>
<pre>	&lt;/ul&gt;</pre>
<pre>&lt;/div&gt;</pre>
The unordered list is styled as a standard navigation menu (A List Apart has a nice article and book about it), and I have it setup to highlight whatever menu item is hovered. To highlight the current page, I set that item to the same background color as the hover effect. A little snippet here:
<pre>/* application.css */</pre>
<pre>a:hover, a:focus { background: #454d2f; }</pre>
<pre>.highlight { background: #454d2f; }</pre>
Now, all that's left is to let jQuery apply the highlight class to the menu item corresponding to the page we're on; an effect I achieve thusly:
<pre>// application.js</pre>
<pre>$('#topnav').ready(function() {
	var page = window.location.href.split("/")[3]; // after the slash at the end of the domain name 
	if (page == "") { page = "home"; }
	$(this).find("a[href$="+page+"]").addClass("highlight"); 
});</pre>
You could do this without jQuery, but it is my favorite JavaScript library and I like to use it :)

Does anyone know of a better way?
