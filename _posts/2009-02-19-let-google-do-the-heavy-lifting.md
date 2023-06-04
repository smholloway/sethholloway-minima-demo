---
layout: post
title: Let Google do the heavy lifting!
alias: /blog/2009/02/19/let-google-do-the-heavy-lifting/
categories:
- Internet
tags:
- analytics
- google
- html
- seth holloway
- wordpress
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I love Google. They represent so many positive ideas about technology and offer an amazing suite of tools. Gmail is fantastic. I adore Google Calendar. Google Scholar is the only site I need for research. Google Reader is the best RSS feed reader on the market. Google Docs works a like a charm and is infinitely handy. I have entrusted my workflow to Google and had positive results. They've taken over the heavy lifting and ushered in an era of browser-based productivity that I agree with wholeheartedly. I'm excited today to use yet another Google server: I added <a title="Google Analytics" href="http://www.google.com/analytics/" target="_blank">Google Analytics</a> to the site :)

In last week's <a title="Randolph Bias' awesome class" href="http://courses.ischool.utexas.edu/Bias_Randolph/2009/Spring/INF385P/" target="_blank">Introduction to Usability course</a> we discussed good and bad websites, and one student selected Google Analytics as a good website. The Analytics page provides all the necessary statistics on your sites traffic including their IP address and corresponding location, the number of unique visitors, and timing. It was characteristically Google: clean, easy to use, and hugely useful. I had no idea the service was free!

Inspired by the class I checked into Google Analytics further and signed up. I added http://www.sethholloway.com to the service and they generated the necessary javascript--they even told me where to place it (though I already <a title="Seth Holloway: Learning HTML/CSS" href="http://sethholloway.com/blog/?p=633" target="_blank">knew enough HTML</a> to insert the scripts)

Here's the generated javascript:
<blockquote>
<pre id="line20">&lt;<span class="start-tag">script</span><span class="attribute-name"> type</span>=<span class="attribute-value">"text/javascript"</span>&gt;
  var gaJsHost = (("https:" == document.location.protocol) ?
                   "https://ssl." : "http://www.");
  document.write(unescape("%3Cscript src='" + gaJsHost +
                          "google-analytics.com/ga.js' 
                          type='text/javascript'%3E%3C/script%3E"));
&lt;/<span class="end-tag">script</span>&gt;
&lt;<span class="start-tag">script</span><span class="attribute-name"> type</span>=<span class="attribute-value">"text/javascript"</span>&gt;
  try {
    var pageTracker = _gat._getTracker("UA-7555904-1");
    pageTracker._trackPageview();
  } catch(err) {}
&lt;/script&gt;</pre>
</blockquote>
And the only change necessary to gather statistics from across the blog is contained in header.php. From your WordPress admin panel click Appearance-&gt;Editor-&gt;Header (header.php). Then locate this bit of code and insert the generated code where I placed the comment below:
<blockquote>
<pre id="line20">&lt;?php if ( is_singular() ) wp_enqueue_script( 'comment-reply' ); ?&gt;

&lt;?php wp_head(); ?&gt;

//PASTE GOOGLE ANALYTICS CODE HERE AND REMOVE THIS LINE

&lt;/head&gt;
&lt;body&gt;
&lt;div id="page"&gt;</pre>
</blockquote>
That's it! So simple! So useful! If you haven't already signed up for Google Analytics, do it now. The service is free, incredibly helpful and easy to use; even better, installation will take you less time than heating up that Hot Pocket!
