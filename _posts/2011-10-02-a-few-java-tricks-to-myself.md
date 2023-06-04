---
layout: post
title: A few Java tricks to myself
alias: /blog/2011/10/02/a-few-java-tricks-to-myself/
categories:
- technical
tags:
- java
- tricks
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
========================================

    if ( foo.equals("bar") ) { // ... }

Here, foo may be null, so instead use

    if ( "bar".equals(foo) ) { // ... }

This pattern generalizes to using the equals method of the concrete object (put the non-null object on the left side).

========================================

You can use instanceof to ensure an object is the proper type (this can replace a null check), as in

    if ( arg1 instanceof String ) { // ... }

========================================

As of Java 1.5 you can declare methods with variable arity, making the syntax a little cleaner and invocation a bit simpler. The old style:

    public static void main(String[] args)

becomes

    public static void main(String... args)

which can then be called like this:

    main("seth", "for", "president")

========================================

Errors and Exceptions derive from Throwable, so you can catch all program hiccups by catching Throwable instead of Exception (or Error).

========================================

Local variables are not initialized with a value; field variables are initialized like so:

Number primitives default to 0.

Objects (Collections) default to null.

Booleans default to false.

========================================

Java has labels, but most people will not appreciate their inclusion and use. For example, the following code is valid Java

    http://www.sethholloway.com

========================================

In mixed-type computation, Java upconverts to the larger data type due to widening primitive conversion. Avoid mixed-type computation and comparisons.

========================================

"Although common, the idiom `object.getClass().getMethod("methodName")` is broken and should not be used." -- <a title="Java Puzzlers sampler" href="http://javapuzzlers.com/java-puzzlers-sampler.pdf">Java Puzzlers sample</a>

========================================

The finally block of a try-catch-finally will always execute (unless there's a hard crash, System.exit(), System.halt(), or infinite loop before). As such, be careful with returns and mutating objects in the try and finally.

========================================
