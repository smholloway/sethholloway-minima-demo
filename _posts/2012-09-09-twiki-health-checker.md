---
layout: post
title: Twiki Health Checker
alias: /blog/2012/09/09/twiki-health-checker/
categories:
- technical
tags:
- github
- javascript
- Twiki
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
A few months ago I got tired of staring at pages of cruft while navigating the Twiki at work. My friend and peer, Otto, suggested that we try to filter those less-than-helpful posts. I couldn't find any tools to help non-administrators, so I figured I'd need to write something myself. That night I wrote some JavaScript to quickly find posts in the Twiki WebIndex that were outdated or written by an unknown author. Once found, the entries are highlighted. The idea was that people would run the code against the Twiki, then delete the marked entries. After a couple code reviews (thanks Derek and Nick!), the script was packaged and put onto GitHub as the <a title="GitHub - Seth Holloway - TwikiChecker" href="https://github.com/smholloway/TwikiChecker">TwikiChecker</a> a.k.a. Twiki Health Checker.

<img class="size-large wp-image-1804" title="TwikiChecker run on Twiki WebIndex" src="/images/delthis-1024x399.png" alt="TwikiChecker run on Twiki WebIndex" width="640" height="249" />

Try running it for yourself on the official Twiki page, <a title="http://twiki.org/cgi-bin/view/TWiki/WebIndex" href="http://twiki.org/cgi-bin/view/TWiki/WebIndex">http://twiki.org/cgi-bin/view/TWiki/WebIndex</a>. (Copy the contents of TwikiChecker.js, navigate to the Twiki WebIndex, open your browser's JavaScript console, paste in the contents and hit enter.)

Hopefully this is useful for others!

Questions or comments? Please let me know via blog comment, email, or pull request.
