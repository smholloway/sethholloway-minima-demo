---
layout: post
title: Hermit crab software
alias: /blog/2013/04/25/hermit-crab-software/
categories:
- technical
tags:
- ease
- idea
- software
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I have spent incalculable amounts of time trying to set up software environments, and if you've done any programming, I'd guess that you have had similar experiences. As a way to save everyone time and frustration, I think we should push for hermit crab software--programming environments that carry their "home" around with them.

<a href="http://andyjthompson.wordpress.com/tag/hermit-crab/"><img class="alignnone" title="Hermit Crab" alt="" src="http://andyjthompson.files.wordpress.com/2010/03/hermit-crab.jpg" width="262" height="264" /></a>

Sometimes you need a language runtime and a text editor, sometimes an IDE has everything, sometimes you have to grab the language and various tools, or the language ecosystem relies on outside libraries. Then there's configuration of each of the components; for example, download and set up the Clojure bundle for TextMate, add the language to your PATH, etc.

Some issues I've had recently:

 * Rails issues like setting up Ruby, Rails, gems, rake, RVM, and fun things like  <a title="Ruby HTTPS error" href="http://stackoverflow.com/questions/9338035/no-such-file-to-load-net-https-heroku-ruby-ubuntu-10-04">Ruby issues with HTTPS that require you to install SSL then reinstall Ruby</a>
 * Persistent Java issues around <a title="StackOverflow: What is Classpath hell?" href="http://stackoverflow.com/questions/373193/what-is-classpath-hell-and-is-was-it-really-a-problem-for-java">jar and classpath hell</a>
 * Exciting new languages like <a title="Scala" href="http://www.scala-lang.org/">Scala</a> and <a title="Clojure" href="http://clojure.org/">Clojure</a> have moved quickly and tutorials have not kept up, so there is confusion.
 * <a title="Sonar Source" href="http://www.sonarsource.com/">Sonar</a> was so easy to install--simply download and unpack--I thought I did it wrong! (There are pitfalls with this type of dead-simple installation, too.)

There are a few promising leads like <a title="Vagrant" href="http://vagrantup.com/">Vagrant</a> and <a title="Ubuntu Juju" href="https://juju.ubuntu.com/">Juju</a>, which make it easier for everyone to share a development environment. Unfortunately, they probably can't help at the language level (e.g., are you using Ruby 1.9.2-p180-patched or 1.9.2-p290?). <a title="Apache Maven" href="http://maven.apache.org/">Maven</a>, <a title="Bundler" href="http://gembundler.com/">Bundler</a>, <a title="Python Installs Packages" href="http://pypi.python.org/pypi/pip">Pip</a>, and other dependency management systems help, but I'd like to see the language make dependencies and versioning a first-class citizen. I envision the ability to download an app from source control and be running with all the right versions of the language, tools, and dependencies in one-click.

So, why not create software environments that carry their environments around on their back?
