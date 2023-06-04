---
layout: post
title: ! 'Rhyme your way to better programs: cache, hash, and thrash'
alias: /blog/2011/09/15/rhyme-your-way-to-better-programs-cache-hash-and-thrash/
categories:
- technical
tags:
- cache
- hash
- optimization
- programming
- thrash
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
There are myriad ways to optimize a program, but you can go a long way with three rhyming concepts:

<a title="Wikipedia: Cache" href="http://en.wikipedia.org/wiki/Cache">cache</a> -  Perform operations once then store them; you trade memory for speed and reduced access to database (for example).

<a title="Wikipedia: Hash table" href="http://en.wikipedia.org/wiki/Hash_table">hash</a> -  Hash maps are fast and efficient for a lot of algorithms; for example, a trie (suffix tree) is faster when implemented as a hash map than as a tree (because insertions and lookup are constant time on average with a hash map but log(n) for trees).

<a title="Wikipedia: Thrashing" href="http://en.wikipedia.org/wiki/Thrashing_(computer_science)">thrash</a> -  Avoid competing for resources, as in database or hard drive lookups.

I thought cache, hash, and thrash was a neat mnemonic. Do you have another go-to for optimizations? Know any other neat mnemonics?
