---
layout: post
title: User scripts in Chrome
alias: /blog/2011/07/07/user-scripts-in-chrome/
categories:
- Internet
tags:
- chrome
- extensions
- greasemonkey
- javascript
- userscripts
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Back in the day I used <a title="Firefox addon: Greasemonkey" href="https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/">Greasemonkey</a> and <a title="Firefox addon: Stylish" href="https://addons.mozilla.org/en-US/firefox/addon/stylish/">Stylish</a> for Firefox--even contributing something to <a title="Userscripts dot org" href="http://www.userscripts.org">userscripts.org</a> (a huge repository of GreaseMonkey and Stylish scripts). Chrome is currently my browser of choice, and I thought of how nice it would be to tweak sites using a little homegrown JavaScript. Turns out, Chrome has Greasemonkey's user script capability built-in.

Any file named &lt;whatever&gt;.user.js will be interpreted as a user script. Simply open the file in Chrome and install it. Now you have a dead simple Chrome extension! As you can see below, there are a couple steps in the install process:

<img class="size-medium wp-image-1373" title="user script install step 1" src="/images/userscript-install-1.png" alt="user script install step 1" />

<img class="size-medium wp-image-1374" title="user script install step 2" src="/images/userscript-install-2.png" alt="user script install step 2" />

<img class="size-medium wp-image-1375" title="user script install step 3" src="/images/userscript-install-3.png" alt="user script install step 3" />

<img class="size-medium wp-image-1376" title="user script install step 4" src="/images/userscript-install-4.png" alt="user script install step 4" />

I created an example user script for Chrome that hides the black bar now appearing that the top of Google sites. I chose Google Reader specifically to demonstrate the @include and @exclude options. You can find it here:  <a href="https://github.com/smholloway/miscellaneous/blob/master/javascript/simple.user.js" title="Seth Holloway's GitHub: simple user script">https://github.com/smholloway/miscellaneous/blob/master/javascript/simple.user.js</a>

If you prefer a more high tech/user friendly version, check out the <a title="Chrome Extension: Personalized Web" href="https://chrome.google.com/webstore/detail/plcnnpdmhobdfbponjpedobekiogmbco#">Personalized Web extension</a> in Chrome.

HT to <a title="Lucas Wiman" href="http://twitter.com/#!/lucaswiman">Lucas</a> for the Personalized Web link and idea for what to demonstrate.
