---
layout: post
title: Analyzing recruiter emails
alias: /blog/2013/05/19/analyzing-recruiter-emails/
categories:
- personal
tags:
- email
- recruiters
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I receive a fair amount of cold calls from recruiters. One night I responded to three emails and realized I could not distinguish between the three within seconds after reading them. Why not you ask? It's not because I'm a weak reader or blew the people off, it's because the emails are so generic!

Below I provide a simple text analysis of emails I received and provide suggestions on how recruiters could be more effective when working with software developers.

<h3>Quick Data Analysis</h3>

  * Examined 91 emails (trimmed down from hundreds)
  * 21 of the emails contained a confidentiality notice -- *gag*
  * 76 used my name
  * 44 opened with "Hi Seth"
  * 50 were sent from self-reported recruiters
  * 2 simply had "resume" in the subject -- I didn't know what to resume, so I couldn't reply (pedantic joke about spelling résumé)
  * I average email was 16009 bytes total
  * 4 used the term 'touch base' which I expected to see more frequently
  * referral bonuses of $500-2000 were explicitly mentioned
  * 6 mentioned their funding (VC backed)
  * 1 mentioned incredible salary (over $150k with a $50k signing bonus)

Recruiter emails are remarkably formulaic. Most contain the phrase "exciting opportunity." Most invite you to forward the opportunity to anyone else you know; this one bugs me every time for two reasons: (1) recruiters are casting a really wide net (in the past, two friends have forwarded me opportunities that the recruiter had already contacted me about) and (2) I feel like I'm doing the recruiter's job if I help them place someone (I don't owe the recruiter any favors and I generally have not been impressed by the job or the way it is presented by the recruiter).

<h3>Suggestions</h3>

Software engineers are highly intelligent, analytical, logical, and highly sought after. Proofread your communications! I've seen misspellings, repeated phrases (coders are familiar with copy/paste errors), weak grammar, and (my pet peeve) incorrectly specified technologies ("Jquery" instead of "jQuery" is my favorite).

Don't say you have a cutting edge position when you don't. How do you know if you're not cutting edge? If you're using years-old technology in a well-known domain, you're probably not cutting edge. Another good indicator: if you're a recruiter! Based on hundreds of recruiter emails it seems that recruiters aren't offering the coolest jobs a company has to offer.

Software interviews are grueling. What are you doing to help me with that?

Too many recruiters seem to get paid to connect job-seekers and businesses, which seems to boil down to forwarding job postings to anyone they can find. Job postings are really easy to find and job-seekers seem really easy to find, so what value does a recruiter add?

If I were to ever work with a recruiter I would want them to show respect. Don't treat people like interchangeable parts or paychecks.

My initial hypothesis was that recruiters are mostly sending the same email making them hard to differentiate. Recruiters should work hard to be different.

Don't say you used to be a 'techie.' If you were, it should be obvious in the interaction. Beyond that, techies don't have to be programmers, they come from all walks of life; for example, my wife is a techie educator and I've met plenty of techie musicians. If you used to be a programmer, you might have cred for a couple years, but that wears off quickly as the industry changes so quickly. Also, if you tell me you used to be a programmer then I immediately wonder why you left: were you bad? does recruiting pay better, and if so, are you just in it for the money?

Have the hiring manager or a recruiting engineer send the job description. I react much better to someone whose title is "Senior Software Engineering" than to someone whose title is "Recruiter, SPHR, MBA, PMP, CIR, CSP, Esq."

Very often, the email would contain job requirements saying things like "Django expertise a must." I've played with Django, but I am by no means an expert--and I can't find anything that connects me with Django (beyond a tenuous link through Python). That leaves me wondering if the job actually requires Django expertise or if the recruiters are setting me up to fail. Either way, I'm not left with a good feeling.

One simple piece of advice: sell something besides a boring job description; people are motivated by mastery, autonomy, purpose, money, commute, calibre of their peers, the ability to work on new features (or improve legacy systems), the ability to work with new technology (hint: Java 1.5 is not new technology). I think you get what you put in, so a company offering a boring job will get boring, workaday people.

Candidates have to differentiate themselves, so why don't recruiters? Here are a few ideas:

  * offer to buy me dinner at my favorite restaurant
  * send me an amazon gift card via email
  * stimulate me on multiple levels
  * conducting business over email and IM
  * open with code or a puzzle
  * stop asking me to forward the message to everyone I know

Also, you know how Google can automatically identify spam? A smart recruiter would create a simple recruiter classifier and ensure that their emails pass through the filter.

Here are a couple simple examples of recruiter pitches that would pique my interest:

<pre>def main() {
   if ( you.are(happyInYourCurrentRole) ) {
        you = lucky;
   } else {
        letsChat();
   }
}
def letsChat() {
    if ( email || linkedIn ) {
        reply();
    } elsif ( phone ) {
        justSayWhen();
    }
}</pre>

Or

"Hey, Seth. I really like your website! You seem to have deep technical knowledge as well as a keen sense of design and usability. Knowing the best programmers, such as yourself, is my business; please enjoy an $25 Amazon gift card and keep me in mind when you're ready for a new job."

<h3>Questions or Comments?</h3>

Did I miss something? Let me know.
