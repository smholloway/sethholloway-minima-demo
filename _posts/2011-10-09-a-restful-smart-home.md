---
layout: post
title: A RESTful smart home
alias: /blog/2011/10/09/a-restful-smart-home/
categories:
- technical
tags:
- actions
- aware home
- conditions
- rails3
- research
- ruby
- rules
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
(I found this in my drafts and thought, "have I really not posted about my PhD research before?" Well, here it is now. Feel free to ask if something is unclear.)

My PhD research was on smart homes (aware homes or intelligent environments). I think of smart homes as <a title="Wikipedia: Even-based Programming" href="http://en.wikipedia.org/wiki/Event-based_programming" target="_blank">event-based</a> systems where <a title="Wikipedia: sensor" href="http://en.wikipedia.org/wiki/Sensor">sensors</a> provide inputs that trigger actions performed by <a title="Wikipedia: actuator" href="http://en.wikipedia.org/wiki/Actuator" target="_blank">actuators</a>. I believe that centralizing the logic creates a direct path forward, which functionally means that individual buildings would have a central server. To this end, I created a smart home server that would accept sensor inputs and create outputs for actuators using a RESTful Web-of-Things style API that should be easy for future devices to conform to (we termed this piece <a title="Sensor Enablement for Average Programmers" href="http://mpc.ece.utexas.edu/SEAP/">SEAP</a>). Users can create their own rules using an interface that we prototyped and tested--it was usable according to our user studies (we termed the complete system <a title="Sensor Enablement for End-Users" href="http://mpc.ece.utexas.edu/SEEU/">SEEU</a>). All of this is available on <a title="GitHub: Seth Holloway - SEEU" href="https://github.com/smholloway/seeu">GitHub</a>.

To implement the server, I used <a title="Ruby on Rails" href="http://rubyonrails.org/" target="_blank">Ruby on Rails 3</a> and <a title="Ruby" href="http://www.ruby-lang.org/en/" target="_blank">Ruby 1.9.2</a> with <a title="jQuery" href="http://jquery.com/" target="_blank">jQuery</a> to speed and simplify JavaScript work. These technologies are fantastic! Devices (sensors and actuators) are modeled using <a title="Wikipedia: Sun SPOT" href="http://en.wikipedia.org/wiki/Sun_SPOT" target="_blank">Sun SPOT</a>s running the <a title="Wikipedia: Squawk VM" href="http://en.wikipedia.org/wiki/Squawk_virtual_machine" target="_blank">Squawk virtual machine</a> (<a title="Wikipedia: Java ME" href="http://en.wikipedia.org/wiki/Java_ME" target="_blank">Java ME</a>, equivalent to ~JRE 1.3). Using our <a title="Sensor Enablement for the Average Programmer" href="http://mpc.ece.utexas.edu/SEAP/" target="_blank">SEAP middleware</a>, sensors <a title="Wikipedia: REST" href="http://en.wikipedia.org/wiki/Representational_State_Transfer" target="_blank">REST</a>fully <a title="Wikipedia: HTTP POST" href="http://en.wikipedia.org/wiki/POST_(HTTP)" target="_blank">POST</a> their values and actuators <a title="Wikipedia: HTTP GET" href="http://en.wikipedia.org/wiki/GET_(HTTP)" target="_blank">GET</a> their state.

And now to the fun part, the rules processing engine. I could not find a rule processing engine in open source projects nor gems/plugins; even the academic research was scarce. So, I developed my own. Rules encode actions triggered by conditions. As I see it, there are two ways to run rules: reactively or periodically. If the rules are run periodically, they are easier to control (e.g., this will run once every minute) but they lose the on-demand factor that people would expect from a lot of operations in a house. Imagine walking into your house with a guarantee that lights will turn on within one minute. No thanks! This would work for something like turning on outside lights in the evening: the front porch lights coming on within one minute of sunset is acceptable. I prefer the more direct approach: reactive rules. The tradeoff here is that rules may run once a second or they may never run. My research prototype ran rules whenever sensor inputs were received, however, I think a periodic component would be useful to guarantee rules were executed.

How often the rules run directly affects your application's performance. I believe rules will be run very frequently, so I chose to store the rules directly (as opposed to storing fragments). This is fast and clear, but it is dangerous because the rules could be malformed and you open yourself to risks of crashing the system or deleting the database (if someone injected malicious code into a rule). There are standard protections against these problems like escaping inputs, employing model checkers, and wrapping execution in try/catch/rescue (or whatever method your language offers). The system had acceptable performance and I fixed any bugs I found with light penetration testing, so I am pleased overall.

Here's a simple grammar for rules given a single sensor and a single actuator:

    R = CA
    C = &lt;sensor&gt; &lt;operator&gt; &lt;value&gt; ... (or conditions logically joined/ANDed together)
    A = &lt;actuator&gt; &lt;value&gt; ... (or actions logically joined/ANDed together)

We derived this grammar by analyzing over 60 rules written by <a title="Seth Holloway: smart home survey" href="http://sethholloway.com/blog/2009/07/30/smart-home-user-study/" target="_blank">survey</a> participants who almost entirely constructed rules in the form of `&lt;if&gt;&lt;condition(s)&gt;&lt;then&gt;&lt;action(s)&gt;`. This was translated to a user interface after a paper prototype test; the best interface determined by user testing was then implemented as the front-end for creating rules in the smart home.

Future work could include more in the grammar, including ranges of values or times. To prevent system failure, a model checker could be employed to ensure that no rules collide. You could potentially optimize the process by synthesizing all simple rules into more complex, correct rules.

Other technical details:

 * I've worked in Microsoft Windows XP, Ubuntu, and Mac OS X, with a heavy slant towards Mac OS X.
 * <a title="Heroku" href="http://heroku.com/" target="_blank">Heroku</a> makes deployment easy and <a title="Git" href="http://git-scm.com/" target="_blank">git</a> plus <a title="Dropbox" href="https://www.dropbox.com/home" target="_blank">Dropbox</a> work beautifully for version control and backups.
 * I developed using text several editors and IDEs including Eclipse, NetBeans, TextEdit, Notepad, TextMate, and Vim.
 * Client-side testing was done using Chrome, Safari, Firefox, and Internet Explorer (sorry Opera!).
 * Code is available <a title="Github: SEEU" href="https://github.com/smholloway/SEEU" target="_blank">here</a>.
