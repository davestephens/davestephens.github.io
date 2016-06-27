---
layout: post
title:  "Monitoring Mystic BBS on Debian"
date:   2016-06-27 00:00
---
I've recently got back into [running a BBS](/bbs) using an awesome piece of software called [Mystic](http://www.mysticbbs.com). 
Whilst it seems incredibly stable out of the box, it can never hurt to have a little bit of monitoring around processes running on your system. With that in mind, I've knocked up an init.d script so that
Mystic will start and stop on boot/shutdown. Additionally, I've leveraged this script with [Monit](https://mmonit.com/monit/)
to provide some process monitoring around Mystic should the worst happen and the process die. I like Monit for its simplicity - it doesn't require a central monitoring server, and will automatically restart processes based on defined triggers. It'll even send you an email when it does something should you want it to.

Let's get Mystic starting and stopping with the system startup/shutdown first, then we'll get Monit installed and monitoring the system, then finally we can configure Monit to keep an eye on Mystic.

Start by switching to root as it'll save you prefixing every command with a sudo:

    sudo -i

Download and install the init script to your system:

    wget https://gist.githubusercontent.com/davestephens/afb321663fa83c9dd0ba83a2b33e75e7/raw/34ff9143d9219a3ccaddcd38fb15aa90aa295e1d/mis
    
Check out the script and ensure the paths are set correctly for your system before you install it - then proceed with the commands below.

    cp ./mis /etc/init.d/mis
    update-rc.d mis defaults

Ensure that Mystic isn't running, then you should be able to start the system:

    service mis start

...and check it's status:

    service mis status

OK cool - so we now have a Mystic BBS that starts and stops with our system. Let's now leverage that init script and configure Monit to keep an eye on things. 

Install Monit:

    apt-get install monit
 
Edit the Monit configuration to start up its web UI and request a username and password:

    nano /etc/monit/monitrc

Remove the hash from the following lines:

    set httpd port 2812 and
        allow admin:monit

Ensure that monit starts correctly, and check its status:

    service monit start
    monit status

You should see something like the following:

    System 'dave-beast'
      status 				Running
      monitoring status 		Monitored
      load average 			[0.00] [0.02] [0.05]
      cpu 				1.5%us 0.9%sy 0.1%wa
      memory usage 			70.0 MB [38.6%]
      swap usage 			0.0 B [0.0%]
      data collected                    Mon, 27 Jun 2016 14:25:47

OK, so we're now set to start configuring Monit to our needs. Monit has a conf.d folder, which is where we can stick all of our custom bits. If you choose to monitor something else, simply create another .conf file with relevant settings, and it'll be included next time you restart Monit. I've saved a generic Mystic config for Monit as a Github Gist, so download that to get started:

    cd /etc/monit/conf.d
    wget https://gist.githubusercontent.com/davestephens/afb321663fa83c9dd0ba83a2b33e75e7/raw/34ff9143d9219a3ccaddcd38fb15aa90aa295e1d/mystic.conf

Let's discuss the config. 

Firstly, we tell Monit to look for the Mystic pidfile. This tells Monit the process ID of the Mystic mis daemon:

    check process mystic with pidfile /mystic/semaphore/mis.bsy
      group mystic

We then tell Monit how to start and stop Mystic, using the init script we set up earlier:

      start program = "/etc/init.d/mis start"
      stop program = "/etc/init.d/mis stop"

Because we can, we'll also check that Mystic is listening on port 23 for telnet connections. Don't forget to edit the port if you use something other than the default.

      if failed host 127.0.0.1 port 23 type tcp then restart

Then just to make sure we don't endlessly restart Mystic if there's a problem, we tell Monit to give up if it restarts 5 times within 5 checks:

      if 5 restarts within 5 cycles then timeout

If it seems simple - that's because it is! Let's restart Monit and check everything looks OK:

    monit restart
    monit status

You'll notice that the output looks similar to before, along with an all new Mystic section:

    Process 'mystic'
      status 			Running
      monitoring status 	Monitored
      pid 			4796
      parent pid 		1
      uid 			1000
      effective uid 		1000
      gid 			1000
      uptime 			5h 13m
      children 			0
      memory kilobytes 		4.6 MB
      memory kilobytes total 	4.6 MB
      memory percent 		2.5%
      memory percent total 	2.5%
      cpu percent 		0.0%
      cpu percent total 	0.0%
      port response time 	0.006s to 127.0.0.1:23 [DEFAULT via TCP]
      data collected            Mon, 27 Jun 2016 15:07:49

For bonus points, hit the web UI at http://computer-hostname:2812, log in with the credentials you specified in the config file and you'll see the same information with the addition of some control buttons. Test them out!

...and that's pretty much it. Easy!

