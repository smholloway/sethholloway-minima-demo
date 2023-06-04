---
layout: post
title: A few thoughts on Ruby
alias: /blog/2011/06/26/a-few-thoughts-on-ruby/
categories:
- technical
tags:
- programming
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
This is not an exhaustive post, just a few thoughts in reaction to reading about and working with <a title="Ruby Lang Dot Org" href="http://www.ruby-lang.org/en/">Ruby</a>.

<a title="Wikipedia: Ruby" href="http://en.wikipedia.org/wiki/Ruby_(programming_language)">Ruby</a>, a dynamic OO language, was developed by Yukihiro "Matz" Matsumoto in the mid '90s. He wanted a powerful, unsurprising language. He borrowed from Perl, Smalltalk, and Lisp (even though <a title="Stege Yegge: Lisp is not an acceptable Lisp" href="http://steve-yegge.blogspot.com/2006/04/lisp-is-not-acceptable-lisp.html">Lisp is not an acceptable Lisp</a>) while trying to focus on usability and following the <a title="Wikipedia: POLA" href="http://en.wikipedia.org/wiki/Principle_of_least_astonishment">principle of least astonishment (POLA)</a>.

Ruby saw it's popularity rise with Ruby on Rails (a popular web framework). Ruby is a really neat language: you can be high-level, you can use functional programming techniques, ... all that good stuff. But enough of the history, here are my likes and dislikes in no particular order:

 * It is really easy to change a variable's type. This is a general gripe with dynamic languages. I generally like the duck-typing, but you need to be disciplined with development practices--just because you can switch from a Fixnum to a String doesn't mean you should!
 * The lack of tail call optimization (TCO)! Just kidding. I borrowed this complaint from people smarter than myself.
 * I hate seeing "TypeError: can't convert Fixnum into String!" I wish Ruby would cast to string automatically; objects have to_s, but you have to explicitly append to_s when outputting non-strings. Ruby knows you're trying to output something as a string and Ruby has a method to cast to a string, so why not do it for me? The better way to output variables is ["variable_name = #{variable_name}"] but I find ["variable_name = " + variable_name] more clear.
 * I don't like returning the last statement in a function without a return keyword. You can write def sum(a,b) a+b; end and have a function that returns a+b. You can also write def sum(a,b) return a+b; end. I find the latter more clear. The problem gets worse when you have complex equations or ternary/inline if statements. Pros will probably understand this, but I have to think twice about what the method does: def foo(a,b) a&gt;0 ? a+b : a-b; end
 * Probably my biggest complaint is lack of explicit information, like parentheses. From the example above, you have parentheses in function definitions, but parentheses are not required for function calls; using our example above, foo a b is equivalent to foo(a, b). When you mix in symbols, default parameters, aliases, and several ways to do the same thing, programs can be very hard to follow. Digging through the Ruby on Rails source has left me scratching my head more than once.
 * I appreciate that introspection/reflection is made simple: just call Object.methods and you know the object's capabilities; call Object.class to find out its class.
 * I get tripped up by the handling of Nil, True, and False. Every object can be evaluated as a boolean, but things like empty strings, empty arrays and hashes, so you end up with lots of conditionals that check for nil or empty. The Rails helper method blank? is nice, but it does not work as expected with booleans. Also all integer values evaluate to true--even 0. As an Electrical/Computer Engineer I think computers have 1s and 0s--not trues and falses--and a 0 should map to false. A nil object is false, but not all false evaluations are caused by a nil; this can necessitate extra processing to determine why the program branched the way it did.
 * I love the range and capability of built-in functions! For example, you can turn any object into a string (Object.to_s). Need to generate permutations, just use <a title="Ruby: Array - Permutation" href="http://www.ruby-doc.org/core/classes/Array.html#M000287">Array.permutations</a>. Dealing with peoples' names? You can use <a title="Ruby: String - Capitalize" href="http://www.ruby-doc.org/core/classes/String.html#M001157">String.capitalize</a> to capitalize the first letter of each word in the string.
 * Sometimes I have to wonder "who named the great built-in functions?" Can the non-standard names be explained by the language creator being Japanese or are the names just strange for me? For example in <a title="Ruby: Array" href="http://www.ruby-doc.org/core/classes/Array.html">Array</a> there are several similar methods like flatten vs flatten! vs to_a vs to_ary, as well as to_s vs inspect. In <a title="Ruby: String" href="http://www.ruby-doc.org/core/classes/String.html">String</a> there's chomp, chop, strip, squeeze... which one trims? Sure, I've learned now but it is not obvious in my opinion.
 * The Ruby convention is that "dangerous" methods are supposed to have an exclamation point, which can get confusing when exclamation points are also the NOT operator. The dangerous methods can act in place or return nil. The return bit breaks consistency because you have to selectively assign variables instead of using a standard pattern. @var = @string.strip! will make @var nil if your @string does not have whitespace (leaving @string unchanged) or it will make @var the stripped string, but @string is also changed. @var is properly assigned if you omit the exclamation point and just use @var = @string.strip.
 * Along the lines of the "dangerous" methods, methods that return a boolean should have a question mark like Object.nil?. Is the following line clear to you? @var.nil? ? @var.strip : @var.strip! A little trivia: the method! and method? is a convention borrowed from Scheme.
 * Operator precedence is tricky; for example, &amp;&amp; is equivalent to and, yet they have different precedence. Similar with or vs ||, not vs !
 * The community is great, but the divide between Ruby and Rails is sometimes too narrow. I recently tried to find a Ruby solution and the top hits were Rails-specific. This isn't bad if you're doing Rails development, and it may be beneficial if patches make it into the language and the framework. I'll be curious to see how this unfolds.

That's all I've got for now! Did I miss something?
