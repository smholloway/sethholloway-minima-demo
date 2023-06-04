---
layout: post
title: Lisp and order of operations (PEMDAS)
alias: /blog/2013/02/02/lisp-and-order-of-operations-pemdas/
categories:
- technical
tags:
- lisp
- math
- pemdas
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Somewhere around third grade I had the order of operations drilled into my head: parentheses, exponent, multiplication, division, addition, subtraction--abbreviated as PEMDAS and pronounced "pem doss." PEMDAS allows you to succinctly communicate mathematical expressions.

5 + 3^2 * 7

Moving through PEMDAS we see there are no parentheses, but there is an exponent: 3^2 == 3*3 == 9. Continuing through PEMDAS we hit the M for multiplication; our example has the middle term multiplied by 7. Finally, we add 5.

Written in a Lisp style the same expression would look something like this:

(+ 5 (* 7 (pow 3 2)))

Rules implicitly encoded in math must be explicitly written in Lisp (or any pre- or post-fix notation for that matter). In various other languages (<a title="REPL.it is a collection of online REPLs" href="http://repl.it" target="_blank">try a few</a>) the order of operations is encoded already.

In a way, it is frustrating that the programming language ignores basic math rules; however, there may be benefits. I wonder, how many bugs would have been avoided by forcing people to use parentheses to group expressions? how much slower was it to type the extra keystrokes? how many future Lispers were snuffed out by explicit mathematics?

How do you feel about the encoding? Does pre-fix notation bother you more in another way?
