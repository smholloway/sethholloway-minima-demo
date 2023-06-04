---
layout: post
title: Thoughts on Learning Clojure
alias: /blog/2013/04/26/thoughts-on-learning-clojure/
categories:
- technical
tags:
- clojure
- fp
- jvm
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
In 2012 I discovered <a title="Rich Hickey on Twitter" href="https://twitter.com/richhickey">Rich Hickey</a> and he blew my mind. I think Hickey is one of the most important computer scientists of our time--we will see this in the next five to years. See his amazing presentations and creations like <a title="Are We There Yet presentation" href="http://www.infoq.com/presentations/Are-We-There-Yet-Rich-Hickey">Are We There Yet?</a>, <a title="Value of Values presentation" href="http://www.infoq.com/presentations/Value-Values">The Value of Values</a>, <a title="Simple Made Easy presentation" href="http://www.infoq.com/presentations/Simple-Made-Easy">Simple Made Easy</a>, <a title="Clojure" href="http://clojure.org/">Clojure</a>, <a title="Datomic" href="http://www.datomic.com/">Datomic</a>, and <a href="http://www.infoq.com/author/Rich-Hickey">more</a>. Fueled by several great videos, I started learning Clojure. Here are my notes from the experience.

 * I like that Clojure builds on Lisp. I feel like I'm working on something cutting edge, yet proven. It feels like joining a dynasty, perhaps.
 * With Clojure, you write right to left, which is new and different. The prefix notation was not intuitive for me.

```javascript
    JavaScript: [1, 2, 3].map(function(i){return i*i;}).reduce(function(a,b){return a+b;});
    Clojure: (reduce + 0 (map #(* % %) '(1 2 3)))
```

 * Map, Reduce, and Filter are really flexible. For example, reduce can be used to implement join really easily. Learning to think this way has not been immediate for me.

    Clojure: (reduce #(str %1 " " %2) '("the", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog"))
    JavaScript: ["the", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog"].join(" ") == ["the", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog"].reduce(function(a,b){return a + " " + b;})

 * Chaining functions together is fun.
 * 2 + 4 is really applying the add function to two arguments (2 and 4). This seems like an obvious statement, but I normally think of the plus sign simply as an operator rather than a function. Clojure, Lisp really, wears new grooves in the brain.
 * It can be hard to get the iterative approach out of my head. For example, Project Euler problems to find the 2,000th prime feels like "generate 2,000 primes and return the last one" and to find the prime after 4,000,000 would be "while the prime is less than 4 million, find the next prime." I had a hard time thinking of these functionally.
 * Lisp can be really clever and readable, and Clojure can be written almost the exact same way. Except that Lisp-style code in Clojure will blow the stack (due to the JVM's lack of ability to tail-call optimize) or perform like crap (the compiler needs "hints" to optimize performance). Suddenly, your beautiful recursive call turns into this less-readable loop-recur mess.
 * Following on the previous point, Lisp can be really unreadable. The language does not layer on any discipline, so the developers better do it. And it turns out that naming functions appropriately is really hard.
 * The standard library is really nice. It is lengthy, which makes it hard to learn.
 * There are a ton of great resources online. They can be woefully out-of-date.
 * In roughly 1 day, I was able to understand more code than I would have expected. I could not do much with that knowledge :)
 * I felt like I had to go to Clojure because it was not coming to me. I believe this reflects Rich Hickey's ethos: he created the language for a reason and wants you to use it in the intended way.
 * It was hard to convince my peers that Clojure was the language of the future. One of the most common questions was, "are there any large system written in Clojure in production?" Based on the reactions, I doubt Clojure will enter the mainstream anytime soon.

Overall, I enjoyed learning Clojure and I feel it made me a better programmer. If you haven't checked it out, <a title="4clojure Problem 1" href="http://www.4clojure.com/problem/1">work through a few problems</a> and see what you think.

Some resources I used along the way:

 * <a title="http://hyperpolyglot.org/lisp" href="http://hyperpolyglot.org/lisp">http://hyperpolyglot.org/lisp</a>
 * <a title="http://www.learningclojure.com/2010/08/reduce-not-scary.html" href="http://www.learningclojure.com/2010/08/reduce-not-scary.html">http://www.learningclojure.com/2010/08/reduce-not-scary.html</a>
 * <a title="https://www.4clojure.com/" href="https://www.4clojure.com/">https://www.4clojure.com/</a>
 * <a title="http://gigamonkeys.com/book/" href="http://gigamonkeys.com/book/">http://gigamonkeys.com/book/</a>
 * <a title="http://moxleystratton.com/clojure/clojure-tutorial-for-the-non-lisp-programmer" href="http://moxleystratton.com/clojure/clojure-tutorial-for-the-non-lisp-programmer">http://moxleystratton.com/clojure/clojure-tutorial-for-the-non-lisp-programmer</a>
 * <a title="https://github.com/relevance/labrepl" href="https://github.com/relevance/labrepl">https://github.com/relevance/labrepl</a>
 * <a title="http://java.ociweb.com/mark/clojure/article.html" href="http://java.ociweb.com/mark/clojure/article.html">http://java.ociweb.com/mark/clojure/article.html</a>
 * <a title="http://www.lisperati.com/clojure-spels/casting.html" href="http://www.lisperati.com/clojure-spels/casting.html">http://www.lisperati.com/clojure-spels/casting.html</a>
 * <a title="http://joyofclojure.com/" href="http://joyofclojure.com/">http://joyofclojure.com/</a>
 * <a title="http://pragprog.com/book/shcloj2/programming-clojure" href="http://pragprog.com/book/shcloj2/programming-clojure">http://pragprog.com/book/shcloj2/programming-clojure</a>
