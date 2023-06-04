---
layout: post
title: Two factor authentication made easy
alias: /blog/2012/06/10/two-factor-authentication-made-easy/
categories:
- Internet
tags:
- authentication
- security
- toopher
- two factor
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Passwords are simply not secure as evidenced by numerous password breaches and numerous hacks. Identity theft is increasingly common and increasingly harmful, so we need to evolve our security sooner rather than later. <a title="Wikipedia: two factor authentication" href="http://en.wikipedia.org/wiki/Two-factor_authentication" target="_blank">Multi factor authentication</a> is a great way to improve security. In essence, we would augment our current password system with an additional factor (something the user possesses--like an RSA token or ATM card--or something unique to the user's person--like a fingerprint or retina scan).

Already, many companies distribute <a title="Two factor authentication - token generators" href="http://en.wikipedia.org/wiki/Two-factor_authentication#Tokens_with_a_display_.28disconnected_tokens.29" target="_blank">RSA fobs</a> that cycle through a unique series of numbers; whenever an employee logs in with the correct password, a secondary check is issued and requires that the user input the number from the RSA device. A few banks offer this system, and <a title="Google offers two factor authentication" href="http://googleblog.blogspot.com/2011/02/advanced-sign-in-security-for-your.html" target="_blank">Google brought the same idea to their authentication system</a>.

Recently, I started using the Google system and I'm pleased overall; however, I know that we can do better. Why require the user to type in an ever-changing key when we can get at that information another way? That is, use the user's phone to verify their location and only allow logins from known locations.

That simple idea is the basis of a company started by my friend and grad school peer, Evan. <a title="Two factor authentication done right " href="https://www.toopher.com/" target="_blank">Toopher</a> is two factor authentication made easy. For my convenience and security, I hope that sites use Toopher!
