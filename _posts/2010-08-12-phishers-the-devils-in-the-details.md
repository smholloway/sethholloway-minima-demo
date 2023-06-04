---
layout: post
title: Phishers, the devil's in the details!
alias: /blog/2010/08/12/phishers-the-devils-in-the-details/
categories:
- Internet
tags:
- blizzard
- games
- phishing
- scam
- security
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _wp_old_slug: ''
---
Phishing is presumably big business (although <a title="Dancho Danchev's analysis of profit in the digital black market" href="http://www.zdnet.com/blog/security/microsoft-study-debunks-profitability-of-the-underground-economy/3522" target="_blank">maybe not</a>). Because email is very cheap to send, phishing has a low barrier for entry. Usually, Gmail's spam filter is so accurate that I don't see the phishing emails, however, recently some Blizzard themed messages have gotten through. I get the impression that the emails are crafted by foreigners who lack the finesse necessary to deceive people--a good thing, no doubt. As with most pursuits, the devil is in the details. Let me illustrate with the most recent email to pierce Gmail's phishing armor:

<blockquote>Hello, thank you for shopping at the Blizzard Store!

StarCraft II®: Wings of Liberty™: 6129523855006794206159153

To use this key to activate the game, simply follow these instructions:
1. Log in to your Battle.n Account - Or Create a <a href="http://us.battle.net.wowsuppor-check-blizzard. com" target="nofollow">Battle.net Account</a>

2. Verify your e-mail address. (If you have previously verified your address, skip this step.) From the main Account Management page, click the 'verify this e-mail address' link. Then, check your e-mail account for a verification e-mail. Click the link in this e-mail to verify your e-mail address.

3. Return to the Battle.net account management page, then click on 'Code Redemption'.
4. Enter the above CDKey in the code field.

5. Once you have successfully redeemed this code, you will be able to play the game.

NOTE: If you have previously chosen to gift your digital purchase, attaching this key to their Battle.net account will prevent you from being able to redeem this key with your Battle.net account.

Order Date: 2010-8-10
Order #: 2573775

(1) StarCraft II®: Wings of Liberty™ - $59.99

Credit Card Number : ****-****-****-9527
Credit Card Type : Vista
Item Subtotal: $59.99
Tax: $0.00
Shipping &amp; Handling: $0.00
Shipping Tax: $0.00
Grand Total: $59.99
===========================================

If you have any questions or concerns about your order, please contact us at:

Phone: Toll-free at (1-800-592-5499)
Website: <a href="http://us.blizzard.net/account" target="_blank">http://us.blizzard.net/account</a>

Live phone support is available seven days a week, 8:00AM - 8:00PM Pacific Time.

Thanks for shopping with us!
Blizzard Customer Service</blockquote>
I like the use of ® and ™! Those are definitely nice touches. However, Blizzard begins by greeting you with the name on the account. Moving on, the CD key should have dashes. Whoops. Next, we see "Battle.n Account - Or Create at Battle.net Account." Within a few words, they misspell Battle.net and give you the proper spelling. Then there's the gratuitous use of capitalization throughout. Seen here on "Account," "Or," and "Create." Throughout, there are a few small, unprofessional and inconsistent bits, like the lack of carriage return between items 3 and 4. Then "CDKey" is lacking a space... Another awesome failure: the "Vis<strong><em>t</em></strong>a" credit card type! A couple lines lower, the "Shipping Tax" itemized seems off.

To be fair, if you were expecting a StarCraft email (sadly, the phishers are two weeks late) and gave only  a quick glance, the email could work. It is apparently sent by Blizzard Entertainment! However, digging deeper in the email header we see more incorrect details:
<blockquote>from	Blizzard Entertainment
to	seth@sethholloway.com
date	Wed, Aug 11, 2010 at 8:46 PM
subject	Battle.net Account Management
mailed-by	hotmail.com</blockquote>
Mailed by hotmail? Phishy. Details, details!

Also, it's important to hover over links before following them... This is probably my favorite part: "wowsuppor-check-blizzard.com." I guess wowsuppor<strong><em>t</em></strong>-check-blizzard.com was already registered :) And, of course, official Blizzard emails direct you to us.battle.net instead of blizzard.com. Details!

Another detail that reeks of fraud is the use of "WoW"/"wow", which refers to another Blizzard product, World of Warcraft. Account management, StarCraft II, and World of Warcraft blend into one weak attempt at phishing.

I believe that every critique should come with a suggestion, so here's my suggestion: buy a legitimate copy of StarCraft II and copy the official email exactly, changing only the link (from official site to your faked site). Then, replicate their website and direct people to the fake. To Blizzard's credit they do not make copying the page easy because they cleverly use dynamically rendered Ajax elements with obfuscated JavaScript and XSLT. They also have a lot of content and they update the pages regularly. Another idea: direct them to your domain, infect their computer with malware, and quickly forward them to battle.net so they're none the wiser.

If you want to step up to the big leagues, you'll have to concentrate on the details!
