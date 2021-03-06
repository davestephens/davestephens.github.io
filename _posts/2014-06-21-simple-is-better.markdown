---
layout: post
title:  "Simple is better"
date:   2014-06-21 20:23:00
categories: update
---

Two things that learning Ruby has taught me:

 * Simple is better.
 * Simple is better.
 
Oh, and, Don't Repeat Yourself. We'll ignore that one for now as I think this is pretty important. Let me elaborate.

My blog was nothing spectacular - a few rambling words here and there
about various things I was working on at various points in time. These words were always written by me, proofed by
me, and published by me. Stuff embedded in posts consisted of code snippets or the odd image or quote by someone. Sometimes
if something popped into my head in the middle of the day, I'd hack a few lines into a draft post during my lunch break and
complete and publish it that evening when I got in.

Yet for some reason, which I think must have been because I thought it was cool to run a PHP application on a Linux box
(we're talking a good 10 years or so ago!), I chose to create my blog using Wordpress. For a while this seemed pretty cool -
it was forcing me to play with Linux (something I'd wanted to learn more about),
I'd learned a bit about MySQL, and some of the drivel I was posting was getting a fair few hits. Awesome.

Fast forward a number of years, a zillion Wordpress updates (and two complete crap-outs after updating),
endless notifications of security vulnerabilities, and running Wordpress was starting to look a lot less attractive.
In addition, with persistent script kiddie attempts of trying to find a hole in the Wordpress version I was using (and
once succeeding), running a seemingly simple blog on Wordpress (and obviously the PHP stack) was taking it's toll on my
poor little VM with run queues frequently sitting somewhere around 10.

With my foray into Ruby (and Rails) like everyone I'd come across Github pages and subsequently Jekyll that powers it. It seemed
like the ideal solution - I write my pages as text files formatted with Markdown, and Jekyll drops out a static HTML site
that I then serve from wherever I decide.

After spending a couple of weeks thinking about the best thing to do, I took the leap and ditched the old Wordpress/PHP
junk and started afresh with a static site generated by Jekyll. This is the first post.

What I've learned/worked out/realised is that I *don't need* a mega-heavy content management system for my little blog. There is *so* much
crud and complexity in Wordpress that I'll never use. There are tonnes of bugs and security holes constantly being found
that require more effort than I can be bothered to spend simply keeping my site alive and my server safe. As my blog is now
in git, it means I can hack on it from wherever I can check into Github - i.e. - everywhere.

So from now on, this is it. Static HTML.

Check yourself before you deploy an overly-elaborate content management system
that you haven't written yourself and that'll probably require constant maintenance. Do you really need it? Probably not.
