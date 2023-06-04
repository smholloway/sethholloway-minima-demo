---
layout: post
title: How to route your Google Site correctly
alias: /blog/2011/04/02/how-to-route-your-google-site-correctly/
categories:
- Internet
tags:
- dns
- domain
- fix
- google
- how-to
- route
- sites
- url
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
TL;DR: check CustomUrl and SitesMappings.

Andrea is hosting her domain, <a title="Andrea Mire Holloway" href="http://www.andreamholloway.com/">andreamholloway.com</a>, on Google Sites. This is yet another great (free) service from Google; however, as with all Google products, you have to find your own way around. For weeks her site was only accessible via the funky, internal Google Sites address (https://sites.google.com/a/andreamholloway.com/www/)--hardly the address you want to share.

We googled for all kinds of keywords with no success. I believe this is a language problem at the core and the problem is particularly difficult because of jargon like DNS, CNAME, ANAME, route, address, URL, site, etc.

In the end, Google has made the process pretty simple. I believe you should only need to check three things

1. Ensure that you are not routing your site administrator/user access to www.&lt;your_domain&gt;
<a href="https://www.google.com/a/cpanel/YOUR_DOMAIN/CustomUrl" target="_blank">https://www.google.com/a/cpanel/YOUR_DOMAIN/CustomUrl</a>

<a href="https://www.google.com/a/cpanel/YOUR_DOMAIN/CustomUrl" target="_blank"></a>Leave your CustomUrl as the default (something like https://www.google.com/a/cpanel/yourdomain.com/)

In this case &lt;your_domain&gt; is the domain you bought.

2. In your SitesMappings, map your Google Site to www.yourdomain.com

<a href="https://www.google.com/a/cpanel/YOUR_DOMAIN/SitesMappings" target="_blank">https://www.google.com/a/cpanel/YOUR_DOMAIN/SitesMappings</a>
Add a new web address
Site Location*
[www]
Web Address*
[www]
Click "Add mapping" button

3. Map the naked domain (yourdomain.com without the www preceding) to www.yourdomain.com

If you did not purchase your domain through Google Sites, you may need to adjust the DNS settings. You'll need to Google around for the right settings, but you will see a lot of ghs.google.com.

For more, I'd recommend you checkout Steegle's guide available <a title="Steegle's Google Sites How-to" href="http://www.steegle.com/websites/google-sites-howtos/googlesites-frequentlyaskedquestionsfaq">here</a>.

I hope this information helps others--I know I spent too much time trying to figure it out myself.
