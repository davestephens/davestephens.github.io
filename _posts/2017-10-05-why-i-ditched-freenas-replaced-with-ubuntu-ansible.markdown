---
layout: post
title:  "Why I Ditched FreeNAS And Replaced It With Ubuntu Server And Ansible"
date:   2017-10-05 00:00
categories: ansible linux ubuntu
---

I've been running a NAS at home since Netgear released the first ARM-powered ReadyNAS device in 2007. It wasn't particularly fast, 
but it did a great job of being a NAS (i.e. keeping my data safe). It also had a decent community following that packaged software 
into easy to install plugins, such as Transmission for downloading torrents and Twonky for serving up media. This worked great until 
I developed a backup plugin that needed to do compression and encryption - then the CPU started to show its age. 

Some point in 2011 I upgraded to an HP Microserver running FreeNAS 8. FreeNAS also had a plugin architecture using FreeBSD jails 
(essentially small chrooted environments for applications to run in), so I could install the software I'd used previously as well as 
some cool new things - Crashplan, Plex, etc. 

This ticked along nicely for a few years until I had a disk failure. I should have heard alarm bells ringing when the second-top Google 
result for "FreeNAS replace failed disk" was a bunch of FreeNAS forum posts with lots of people asking the same thing over and over, 
each with similar (but not the same results!). The top Google result are the FreeNAS docs, and they are *dreadful*. 
Searching "zfs replace failed disk" yielded slightly better results and at least some readable documentation.

I eventually made my way to FreeNAS 9 but yet more hardware failures followed, 
this time the USB stick with the FreeNAS system partition on it crapped out. Data still intact (and a full backup stashed 
away in Crashplan), but no OS to read it. FreeNAS Corral had been out about a month at that point, so I fired up a fresh 
USB stick and loaded it on. Thankfully it was reasonably trivial to import my data and everything was up and running after a few hours. 

Then I tried to reboot it.....and waited. And waited. Hmmm. Must be a one off. Power off, try again...another hang. 
Try again...wait...and eventually it came online and everything seemed ok. Unfortunately (for me), within a few days FreeNAS Corral 
started to show its immaturity - the web UI would become unresponsive, it'd randomly drop off the network, 
the reboot instability continued, and the CPU would get mashed when it was seemingly sat there idle. Then...THEN, the guys at 
iXSystems decided that [FreeNAS Corral wasn't a real release after all](https://www.theregister.co.uk/2017/04/18/freenas_downgrades_latest_release_to_tech_preview/), 
but it was actually a "tech preview". Wait, what?

It was at this point I thought "why on earth am I bothering with this crap?" - my career is based around building stable systems 
that process obscene amounts of data, so I should put this into practise and build something simple that "just works". 

And I did. 

[Ansible-NAS](https://github.com/davestephens/ansible-nas) is as simple as it gets whilst being packed with features - a barebones Ubuntu LTS image, Samba for sharing data, 
Linux ZFS so I could just import my ZFS disk pools with minimal messing about, and best of all - a Docker host to run up whatever 
I please at any point in time. Not a crappy FreeNAS-style unstable Docker host, but a real one that works and stays online. With the 
flexibility Docker brings, I've included a bunch of (switchable) Docker images that most people running their own NAS would find useful:

- Transmission for downloading torrents
- Crashplan for data backup
- Couchpotato for managing movies
- Sonarr for managing a music collection
- Glances for a quick web-based view of the system status
- Portainer for managing the Docker host and running ad-hoc containers

I've been running it myself now for a few months, and guess what? It's rock solid. 

[Try it out](https://github.com/davestephens/ansible-nas) and let me know what you think. If there's something missing you'd love to 
see added, submit a pull request - contributions are welcome!
