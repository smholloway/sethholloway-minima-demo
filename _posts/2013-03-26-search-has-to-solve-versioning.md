---
layout: post
title: Search has to solve versioning
alias: /blog/2013/03/26/search-has-to-solve-versioning/
categories:
- technical
tags:
- search
- versioning
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Search has been failing me frequently in the recent past, and the problem is only getting worse. Versions are everywhere and search is not keeping up. Here are a few examples:

 * Googling for "mac lion" returns 5 results for Lion and 5 for Mountain Lion on the first page. Specifying version number (e.g., "mac lion 10.7") or date (e.g., "mac lion 2011") does not particularly help the results.
 * World of Warcraft has repeated some items with each expansion (or retooled bosses like Onyxia and even whole zones like Naxxramus). Searching for the item may lead you to the 2010 incarnation. Simply adding 2012 or the expansion name is often ineffective because the pages will contain dates and expansion names throughout the content. Another example: there are over <a title="Fortune Card -- what version???" href="http://www.wowhead.com/item=60840/fortune-card">50 virtually identical fortune cards</a>.
 * A similar idea occurs in GitHub branches. For example, if you're looking for <a title="Toopher Ruby" href="https://github.com/toopher/toopher-ruby">Toopher's Ruby client</a> (which rocks!) then you might find my fork that was already merged with master.
 * In my personalized search results for "cross platform password management," Google returns an outdated <a title="Outdated -- Lifehacker's five best password managers" href="http://lifehacker.com/5042616/five-best-password-managers">Lifehacker article from 2008</a> above more recent articles. In this case, recency trumps Lifehacker's relevance and authority.
 * While learning Clojure (at version 1.4) I kept finding StackOverflow responses like, "here's how to do it in Clojure 1.2." The more dangerous response was "here's how to do it in Clojure" with no mention of versioning. I spent hours trying to get the outdated procedures to work only to have them fail.
 * There are bugs that exist for certain operating systems with certain versions of dependent projects. Like <a title="Ruby 1.9.2 seg faults with OpenSSL" href="http://www.christopherirish.com/2011/09/02/ruby-1-9-2-segmentation-fault-and-openssl/">Ruby 1.9.2+ on Mac OS X Lion when installed with RVM 1.0 or higher</a>. Searching for this was difficult because it required so many versions.

Some of these examples would be prevented by using advanced search options and narrowing results to the past year; however, I feel that's a cop-out for a poor user experience.

Until search engines gain additional processing, I think we should get familiar with scoping search results and ask that answers contain version information for increased searchability.

I think search has to solve versioning--what do you think?
