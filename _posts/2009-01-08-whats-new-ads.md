---
layout: post
title: What's new? Ads!
alias: /blog/2009/01/08/whats-new-ads/
categories:
- technical
tags:
- ads
- adsense
- google
- how-to
- tutorial
- wordpress
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I hope my lovely, intelligent readers do not mind the two new ad panels (at the bottom of individual posts and in the sidebar); RSS readers should not notice any changes. This was a fun technical project that may make me a dollar over about twenty years :)

Here's how I added ads to the sidebar and the end of single posts in my WordPress blog. You may be able to do it easily with a plugin, such as one of the <a title="Wordpress Plugins for AdSense" href="http://www.quickonlinetips.com/archives/2006/11/10-best-wordpress-plugins-for-google-adsense/" target="_blank">ten featured in this article</a>, but I chose to do it manually to learn more.

For ease, I used two tabs. In one tab I generated ads and another tab was used to edit pages.

<strong>Generating Ads.</strong> Google makes it easy with <a title="Google AdSense" href="https://www.google.com/adsense/" target="_blank">AdSense</a>. You can see your options for ads <a title="AdSense Ad Formats" href="https://www.google.com/adsense/static/en_US/AdFormats.html" target="_blank">here</a>. First, sign up for AdSense then enter the AdSense Setup page, the <a title="Google AdSense Get Ads" href="https://www.google.com/adsense/adsense-products" target="_blank">Get Ads tab</a>. Both my units are AdSense for Content; one Ad Unit and one Link Unit. After choosing the options I wanted, I was given sample code. I copied this code and switched to the other tab.

<strong>Editing Pages.</strong> First, get to the Theme Editor:

 * Log into the administrative panel.
 * Click the <em>Design</em> tab
 * Click the <em>Theme Editor</em>

I put the banner ad at the bottom of the single post. To do so I copied the generated code then performed these steps:

 * Selected <em>Single Post (single.php)</em>
 * Pasted the following code above the line "&lt;?php get_footer(); ?&gt;":

<blockquote>&lt;!--- Ad support. Added by Seth Holloway on Jan 9, 2009 ---&gt;
&lt;div id="ads"&gt;
&lt;script type="text/javascript"&gt;&lt;!--
google_ad_client = "pub-2003017988956692";
/* 728x90, created 1/8/09 */
google_ad_slot = "5798236936";
google_ad_width = 728;
google_ad_height = 90;
//--&gt;
&lt;/script&gt;
&lt;script type="text/javascript"
src="http://pagead2.googlesyndication.com/pagead/show_ads.js"&gt;
&lt;/script&gt;
&lt;/div&gt;</blockquote>
For the sake of looks, I then needed to edit the stylesheet in the following manner:

 * Selected the <em>Stylesheet (style.css)</em>
 * Added this to the code:

<blockquote>/* Ad support. Added by Seth Holloway on Jan 9, 2009 */
#ads {
text-align: center;
}</blockquote>
I then generated the sidebar link unit, copied the code, and followed these steps:

 * Selected the <em>Sidebar (sidebar.php)</em>
 * Pasted the generated ad unit to the code above the final "&lt;/ul&gt;":

<blockquote>&lt;!--- Ad support. Added by Seth Holloway on Jan 9, 2009 ---&gt;
&lt;li&gt;
&lt;script type="text/javascript"&gt;&lt;!--
google_ad_client = "pub-2003017988956692";
/* 120x90, created 1/8/09 */
google_ad_slot = "2887058896";
google_ad_width = 120;
google_ad_height = 90;
//--&gt;
&lt;/script&gt;
&lt;script type="text/javascript"
src="http://pagead2.googlesyndication.com/pagead/show_ads.js"&gt;
&lt;/script&gt;
&lt;/li&gt;</blockquote>
And voila! We now have two unobtrusive ads on sethholloway.com.

Later, I would like improve the relevance of the ads and to add Digg, Reddit, and Sharethis buttons.

Any tips for items missing from the blog? Did you notice the ads? Do you hate them?
