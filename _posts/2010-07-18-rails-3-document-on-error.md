---
layout: post
title: Rails 3 document.on error
alias: /blog/2010/07/18/rails-3-document-on-error/
categories:
- Internet
tags:
- html
- prototype
- rails
- rails3
- ruby
- ruby187
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _wp_old_slug: ''
---
I'm working through <a title="Agile Web Development with Rails" href="http://pragprog.com/titles/rails4/agile-web-development-with-rails" target="_blank">Agile Web Development with Rails, 4th Edition</a>. Overall, the book is well written--readable, nice depth and breadth, great example (ecommerce site)--and I would recommend it highly; however,  Chapter 11, adding Ajax support to the cart, has given me hell.

I spent hours working through the example a couple times, diffing my source against the <a title="Agile Web Development with Rails source code" href="http://pragprog.com/titles/rails4/source_code" target="_blank">source code provided</a>, starting and restarting the server, trying multiple browsers (Safari, Firefox, Chrome), grepping for errors,  and googling. Finally, I arrived at the solution:

To remedy this problem, I updated my public/javascripts/prototype.js file from the <a href="http://www.prototypejs.org/download" target="_blank">prototype download page</a>. At the time of writing, that was <a href="http://prototypejs.org/assets/2010/5/13/prototype.js" target="_blank">http://prototypejs.org/assets/2010/5/13/prototype.js</a>

<strong>Debugging</strong>

Here are the steps I followed to track down the problem.

First, I noticed that the page was refreshing everytime I pressed an "Add to Cart" button. I made sure the necessary files were in place and the javascript input was defined for the create method I was Ajaxifying. To ensure the button was properly defined, I viewed source and ensured the element had an attribute <em>data-remote="true".</em> Despite proper HTML and Ruby, the development.log showed that I was still retrieving the page as HTML instead of JavaScript
<blockquote>Started POST "/line_items?product_id=3" for 127.0.0.1 at Sun Jul 18 21:06:41 -0500 2010
Processing by LineItemsController#create as HTML
Parameters: {"product_id"=&gt;"3", "authenticity_token"=&gt;"Dsv044fqfo7H46jLYx3e6qnbCgqk3Tcoij6pqbOQZx4="}</blockquote>
So I checked the browser errors. Firefox showed
<blockquote>Error: document.on is not a function
Source File: http://localhost:3000/javascripts/rails.js?1277734011
Line: 136</blockquote>
Inspecting the element in Chrome I saw
<blockquote>Uncaught TypeError: Object #&lt;an HTMLDocument&gt; has no method 'on'</blockquote>
Looking at the rails.js file, line 136, we see
<blockquote>
<pre>  document.on("click", "*[data-confirm]", function(event, element) {
    var message = element.readAttribute('data-confirm');
    if (!confirm(message)) event.stop();
  });</pre>
</blockquote>
Between the errors and the rails.js file, we see that none of the included JavaScript files nor the browser defined the method. A new <a title="Rails 3 Patch" href="https://rails.lighthouseapp.com/projects/8994/tickets/5109-make-prototypejs-compatible-with-railsjs-for-30" target="_blank">Rails 3 patch</a> will upgrade prototype from 1.6.1 to 1.7rc2, so future generations will not experience this fun.
