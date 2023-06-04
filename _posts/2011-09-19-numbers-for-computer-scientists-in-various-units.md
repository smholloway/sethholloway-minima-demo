---
layout: post
title: Numbers for Computer Scientists in various units
alias: /blog/2011/09/19/numbers-for-computer-scientists-in-various-units/
categories:
- technical
tags:
- numbers
- seconds
- timing
- units
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _aioseop_description: The so-called Jeff Dean numbers in various units (nanoseconds,
    microseconds, milliseconds, and seconds).
  _aioseop_title: Numbers for Computer Scientists in various units
  _aioseop_keywords: jeff dean, computer science, numbers, timing, seconds, units
---
These are the so-called <a title="Jeff Dean: Google Badass" href="http://research.google.com/people/jeff/index.html">Jeff Dean</a> <a title="Quora: What numbers should computer people know?" href="http://www.quora.com/What-are-the-numbers-that-every-computer-engineer-should-know-according-to-Jeff-Dean">numbers that computer scientists should understand when tuning for performance</a> (for example, you can see that pulling data from the L1 cache is much faster than retrieving it over the Internet). The nanosecond conversion slows me down, so here's a chart in the spirit of "don't make me think"
<pre>L1 cache reference
          0.5 ns | 0.0005 us  | 0.0000005 ms | 0.0000000005 s
Branch mispredict
            5 ns | 0.005 us   | 0.000005 ms  | 0.000000005 s
L2 cache reference
            7 ns | 0.007 us   | 0.000007 ms  | 0.000000007 s
Mutex lock/unlock
           25 ns | 0.025 us   | 0.000025 ms  | 0.000000025 s
Main memory reference
          100 ns | 0.1 us     | 0.0001 ms    | 0.0000001 s
Compress 1K bytes with Zippy
        3,000 ns | 3 us       | 0.003 ms     | 0.000003 s
Send 2K bytes over 1 Gbps network
       20,000 ns | 30 us      | 0.03 ms      | 0.00003 s
Read 1 MB sequentially from memory
      250,000 ns | 250 us     | 0.25 ms      | 0.00025 s
Round trip within same datacenter
      500,000 ns | 500 us     | 0.5 ms       | 0.0005 s
Disk seek
   10,000,000 ns | 10,000 us  | 10 ms        | 0.01 s
Read 1 MB sequentially from disk
   20,000,000 ns | 20,000 us  | 20 ms        | 0.02 s
Send packet CA-&gt;Netherlands-&gt;CA
  150,000,000 ns | 150,000 us | 150ms        | 0.15 s</pre>
If the above table formatting does not work for you, maybe you'll prefer this one:
<pre>ACTION                                 ns   |   us    |   ms
L1 cache reference                      0.5 |  0.0005 | 0.0000005
Branch mispredict                         5 |   0.005 | 0.000005
L2 cache reference                        7 |   0.007 | 0.000007
Mutex lock/unlock                        25 |   0.025 | 0.000025
Main memory reference                   100 |     0.1 | 0.0001
Compress 1K bytes with Zippy          3,000 |       3 | 0.003
Send 2K bytes over 1Gbps             20,000 |      30 | 0.03
Read 1MB  from memory               250,000 |     250 | 0.25
Roundtrip within same datacenter    500,000 |     500 | 0.5
Disk seek                        10,000,000 |  10,000 | 10
Read 1MB sequentially from disk  20,000,000 |  20,000 | 20
Send packet CA-&gt;NL-&gt;CA          150,000,000 | 150,000 | 150</pre>

