---
layout: post
title: A few programming notes to myself
alias: /blog/2011/09/22/a-few-programming-notes-to-myself/
categories:
- technical
tags:
- java
- javascript
- notes
- python
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _wp_old_slug: a-few-programmingnotes-to-myself
---
In JavaScript, if on a non-boolean input will check existence. In Ruby, the same test will also check for existence with "" considered true; you receive a warning (warning: string literal in condition). Python performs like JavaScript. In Java, you receive a type error (Type mismatch: cannot convert from String to boolean). I show the output from JavaScript console, irb, python, and Java.

JavaScript
<pre>&gt; if ("false") { console.log("true"); } else { console.log("false"); }
true</pre>
<pre>&gt; if ("") { console.log("true"); } else { console.log("false"); }
false</pre>
Ruby
<pre>puts "false" ? "true" : "false"
(irb):4: warning: string literal in condition
true</pre>
<pre>&gt; puts "" ? "true" : "false"
(irb):1: warning: string literal in condition
true</pre>
Python
<pre>&gt;&gt;&gt; if ("false"):
...     print "true"
... else:
...     print "false"
...
true</pre>
<pre>&gt;&gt;&gt; if (""):
...     print "true"
... else:
...     print "false"
...
false</pre>
Java
<pre>if ("false") {
    System.out.println("true");
} else {
    System.out.println("false");
}

Exception in thread "main" java.lang.Error: Unresolved compilation problem:
Type mismatch: cannot convert from String to boolean</pre>
No matter how the language handles it, it's bad coding style because of erratic behavior. Save the next programmer some grief and specify the full expression whose truthiness you are seeking.

====================

JavaScript is not multi-threaded; the spec does not specify any threading or synchronization. JavaScript in modern browsers is single-threaded. Handling multiple actions at once is done by firing off functions and waiting for callbacks.

====================

In Java, the default equals method will compare the memory location of two objects; the default hashcode implementation will return the memory address.

====================

In Java, all data structures in Collections offer a method, size(), to access the data structure's size. Primitive arrays have a property, length (note the difference in name and method vs property). Strings use a method, length(), to make things more confusing!
<pre>List&lt;Integer&gt; list = new ArrayList&lt;Integer&gt;();
System.out.println(list.size());
0</pre>
<pre>int array[] = new int[10];
System.out.println(array.length);
10</pre>
<pre>String string = new String();
System.out.println(string.length());
0</pre>
====================

One way to implement a fixed-size cache is to store elements twice: one in a hash map and one in a linked list. To add an element, first check size; if you're at capacity, remove the oldest element (the head of the linked list) from both structures, then insert the element into both data structures (at the end of the linked list and at the proper location in the hash map). This can be done in constant time. The contains() method is a simple hash map look-up in constant time. This data structure optimizes overall run time [O(n)] at the cost of storing elements twice.

====================
