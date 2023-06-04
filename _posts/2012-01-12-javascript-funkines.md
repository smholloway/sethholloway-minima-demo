---
layout: post
title: JavaScript funkiness
alias: /blog/2012/01/12/javascript-funkines/
categories:
- Internet
tags:
- gotchas
- javascript
- programming
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
JavaScript is an awesome language! It is multi-paradigm and absolutely ubiquitous (available on almost every computer through the browser). As I explore JavaScript further, I find more and more oddities. While I'm thinking about it, I thought I'd write a few out. These gems are a combination of my experience and threads on StackOverflow.

<pre> var whatDate = new Date(2012, 25, 1);
 console.log(whatDate.getFullYear());
 2014</pre>

<pre> var now = new Date();
 console.log(now.getFullYear());
 console.log(now.getYear());
 console.log(now.getDate());
 2012
 112
 12</pre>

<pre> 5 + 3
 8
 5 - -3
 8
 5 - 3
 2
 "5" - 3
 2
 "5" + 3
 "53"</pre>

<pre>var test = function()
{
  return
  {
    id: 1,
    title: "seth"
  };
}
test();
SyntaxError: Unexpected token :

var test = function() {
  return {
    id: 1,
    title: "seth"
  };
}
test();
Object</pre>

<pre>'' == '0' // false
0 == '' // true
0 == '0' // true
false == 'false' // false
false == '0' // true
false == undefined // false
false == null // false
null == undefined // true
" \t\r\n" == 0 // true</pre>

<pre>console.log(parseInt("05"))
5
console.log(parseInt("08"))
0
console.log(parseInt("010"))
8</pre>

<pre>3.toString();
SyntaxError: Unexpected token ILLEGAL
3..toString();
"3"</pre>

<pre>2 == [[[2]]]
true</pre>

<pre>parseInt("hello")
NaN
1/0
Infinity

undefined = 42;
Infinity = "beyond"
NaN = 1;
console.log(42 == undefined)
console.log("NaN (not a number) = " + NaN);
true
NaN (not a number) = 1</pre>

<pre>myHash = {"my" : "hash"}
console.log(myHash.my);
console.log(myHash["my"]);
hash
hash</pre>

<pre>var i = 0
a = new Array();
a[i++] = i
1</pre>

<pre>var dog = "rufus"
!!dog
true</pre>

<pre>var a = 1;
var func = function() {
  a = 2;
  if ( false ) {
    a = 3;
  }
}
console.log("before func() a = " + a);
func();
console.log("after func() a = " + a);
before func() a = 1
after func() a = 2

var func = function() {
  var a = 1;
}
a = 2;
console.log("before func() a = " + a);
func();
console.log("after func() a = " + a);
before func() a = 2
after func() a = 2</pre>

<pre>if ( "Seth" ) { console.log("true"); }
if ( 2+2 ) { console.log("true"); }
if ( {} ) { console.log("true"); }
true
true
true</pre>


[http://stackoverflow.com/questions/1995113/strangest-language-feature](http://stackoverflow.com/questions/1995113/strangest-language-feature)
[http://stackoverflow.com/questions/1724255/why-does-2-2-in-javascript](http://stackoverflow.com/questions/1724255/why-does-2-2-in-javascript)

Have you encountered other gotchas or been bitten by anything else in JavaScript?
