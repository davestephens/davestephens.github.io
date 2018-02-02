---
layout: post
title:  "ENiGMA½ BBS Docker Image"
date:   2018-02-02 00:00
categories: enigma-bbs bbs docker 
--- 
I'm a big fan of the [open source BBS software](http://enigma-bbs.github.io) ENiGMA½ BBS and have been using it to run 
[fORCE9 BBS](https://bbs.force9.org) for about a year and a half. The project is great - run by [Bryan Ashby](https://l33t.codes/) I've 
seen it develop from just supporting mail, to also supporting file bases, netmail, built in door server connections as well as tonnes of
other cool stuff. I've also contributed a few bits and bobs of my own to the project...

One thing missing for me was an easy way to deploy, upgrade and roll back the code. I like Docker, so set 
about creating an image that comes packed with all of the dependencies you need to get ENiGMA½ up and running with as minimal effort as 
possible. 

You can find the ENiGMA½ Docker image [here](https://hub.docker.com/r/davestephens/enigma-bbs/) - but if you're keen to try it out,
simply run the following and connect to port 8888 of your Docker host with your favourite telnet client:

```
docker run -d \
  -p 8888:8888 \
  davestephens\enigma-bbs
```

Enjoy!
