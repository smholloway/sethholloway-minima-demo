---
layout: post
title: Flash, you sneaky bastard!
alias: /blog/2010/02/21/flash-you-sneaky-bastard/
categories:
- Internet
tags:
- flash
- Internet
- security
- sneaky
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
<a title="Wikipedia: Flash" href="http://en.wikipedia.org/wiki/Adobe_Flash" target="_blank">Flash</a>, the popular multimedia platform that helps make websites more interactive, has cookies separate from your web browser's cookies. They're called <a title="Wikipedia: Local Shared Object" href="http://en.wikipedia.org/wiki/Local_Shared_Object" target="_blank">local shared objects (LSO)</a> and they may be a security hole--like all things Flash ;-)

There are a number of directories where the flash cookies may be stored. For example, on Mac OS X, LSOs are stored in two locations:

 * ~/Library/Preferences/Macromedia/Flash\ Player/#SharedObjects/
 * ~/Library/Preferences/Macromedia/Flash\ Player/macromedia.com/support/flashplayer/sys/

And there are more possible! For a detailed list, check the <a title="Wikipedia: LSO#File Locations" href="http://en.wikipedia.org/wiki/Local_Shared_Object#File_locations" target="_blank">list of locations on Wikipedia's LSO entry</a>.

You can manually navigate to these locations and delete nasty ad-tracking/malware-hosting objects; however, while deleting unwanted cookies is worthwhile, it's not a good long-term solution. I recommend you <a title="Flash Controls" href="http://www.macromedia.com/support/documentation/en/flashplayer/help/settings_manager02.html" target="_blank">update your Flash settings</a> (this interface also allows you to delete your LSOs) now! There are several tabs to look through, but don't worry--it's quick. Make sure you deny access to your camera and microphone! For finer grained control, the Firefox extension <a title="Objection Firefox Addon" href="http://objection.mozdev.org/" target="_blank">Objection</a> helps track and <a title="GHacks: Delete Flash Cookies" href="http://www.ghacks.net/2008/07/30/delete-flash-cookies/" target="_blank">eliminate Flash cookies</a>.

Whatever your strategy, I wish you luck!
