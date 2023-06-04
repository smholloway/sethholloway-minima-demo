---
layout: post
title: Do we need AV software?
alias: /blog/2008/12/14/do-we-need-av-software/
categories:
- Internet
tags:
- antivirus
- security
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Do we need AV software? It is naive to think that safe practices will protect you--there are simply too many ways to get into a system. You need something to protect your computer, and good AV software won't hurt.

I was reading a lifehacker article <a title="Lifehacker: Do you use AV software?" href="http://lifehacker.com/384147/do-you-run-antivirus-software?cpage=2" target="_blank">asking readers about antivirus (AV) software</a>. The range of knowledge conveyed in the comments is ridiculous. Some users claimed they never had a virus. There are known botnets with over a million machines. I doubt that all million machines are owned by a single individual, which means there are multiple users who are either willingly allowing someone to use their machine, or the multiple users are unaware of the heist. With the sophistication of modern viruses (rootkits, automatic replication, dynamic signature changing, etc), it is silly to claim you would even know if you had a virus.

A couple users claim that there had never been a virus for Linux. I don't even know where to start on that one. Definitely false. Any script kiddie could gain access to a Linux system that had not been hardened. There are a number of measures a system administrator can take to mitigate threats on Linux, but not every Linux user is a sys admin. Services like ssh being on by default increase the risks greatly. The power of a Linux command line and access to powerful development tools make subsequent attacks easier to launch.

People seem to define virus strangely. Some viruses like vundo trigger a lot of pop-ups, but won't necessarily crater your system. Other viruses that do not brick your machine are passively collecting information, waiting for further instructions, or launching attacks. You don't even have to open a file to be at risk. You don't even have to be online; infected USB keys (and other input devices) can infect a computer that isn't online.

It's not just dumb users either. Viruses come from your friends and people you trust. Elaborate social networking hoaxes are being performed everyday, and everyday they get more convincing. Malware distributors have some of the most professional websites online. Their UI and interface design mimic trusted providers so a quick glance will not immediately reveal a problem. You have to realize and appreciate the ingenuity of the nefarious Internet warriors--they're smart, creative, and talented.

Comparisons have shown that no one piece of antivirus software will catch all viruses, so your best bet is to

1) be safe:

 * Don't open links in emails. Type the URL into the address bar on your own.
 * Be mindful of what your friends are sending you. Would Suzy really send you a link to get rich quick?
 * Avoid the worst of the web (pornography, gambling, warez)

and 2) run a few different tools:

 * <a title="AVG Free" href="http://free.avg.com/download-avg-anti-virus-free-edition" target="_blank">AVG</a> (or <a title="avast! Home Edition (free)" href="http://www.avast.com/eng/download-avast-home.html" target="_blank">avast!</a>) - Antivirus
 * <a title="Peer Guardian 2" href="http://phoenixlabs.org/pg2/" target="_blank">PeerGuardian 2</a> - IP Blocker
 * <a title="Ad-Aware" href="http://www.lavasoft.com/products/ad_aware_free.php" target="_blank">Ad-Aware</a> - Antispyware

So do we need AV software? Yes. You can never be totally safe, but you can mitigate your risks. Use common sense, a few tools, and perform frequent backups. Good luck!
