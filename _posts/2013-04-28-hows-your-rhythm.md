---
layout: post
title: How's your rhythm?
alias: /blog/2013/04/28/hows-your-rhythm/
categories:
- personal
tags:
- metronome
- music
- rhythm
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
This weekend I wrote <a title="Seth Holloway: Rhythm test" href="http://sethholloway.com/timing.html">a simple webpage to measure the accuracy of my rhythm</a> (the <a title="GitHub: JavaScript timing project" href="https://github.com/smholloway/miscellaneous/tree/master/javascript/timing">timing project on GitHub</a>). Just load the page then start tapping any key(s) periodically; the page records and reports on the time between key-presses.

In playing with the page my standard deviation normally hovered around 20ms, drifting up towards 40ms. This was without a metronome.

Open questions:

 * What is a good accuracy?
 * How long should a rhythm test last? Five seconds seems too short and five minutes seems too long.
 * Am I reporting the proper statistics?
 * Is my quick attempt at measuring rhythm flawed? JavaScript may be too slow or imprecise. Are there bugs?
 * How can the app be improved?

How's your accuracy? Got any ideas? Please let me know!
