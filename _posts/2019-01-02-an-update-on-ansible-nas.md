---
layout: post
title:  "An Update On Ansible-NAS"
date:   2019-01-02 00:00
---
Its been over a year since I last wrote about Ansible-NAS, and a lot has changed since then. Most notably, people are actually using and contributing to the project. For something that I started to solve a problem of my own, this is awesome! It would appear that I'm not alone in finding FreeNAS a massive overkill for a home server setup, or in wanting to build my own server rather than buying an off-the-shelf product.

Some of the more notable changes:

* ***Documentation*** - Documentation is generated using mkdocs, and can be found [here](https://davestephens.github.io/ansible-nas).
* ***Support Chat*** - As much as I'd love to use IRC, the GitHub integration isn't there and IRC has a high barrier to entry for new users, so I went with [Gitter](https://gitter.im/Ansible-NAS/Chat).
* ***Tests*** - Ansible-NAS's tests run on every commit via the awesome [Travis CI](https://travis-ci.com/davestephens/ansible-nas). It's also now possible to spin up a local instance using Vagrant.
* ***Remote Access*** - Access to your Ansible-NAS box is available from outside your home network, using [Traefik](https://traefik.io/). Traffic is encrypted using certificates from [Let's Encrypt](https://letsencrypt.org/). [Guacamole](https://guacamole.apache.org/) provides remote desktop access to Linux and Windows computers you may have at home.
* ***Home Dashboard*** - All applications installed on your server are available via [Heimdall](https://heimdall.site/).
* ***Statistics and Monitoring*** - [Grafana](https://github.com/grafana/grafana), [InfluxDB](https://github.com/influxdata/influxdb) and [Telegraf](https://github.com/influxdata/telegraf) work together to provide a powerful monitoring solution.
* ***Automatic Updates*** - [Watchtower](https://github.com/v2tec/watchtower) checks for Docker image updates, and automatically pulls and restarts applications.
* Lots more applications through the work of myself and Ansible-NAS's contributors - [Emby](https://emby.media/), [Gitea](https://gitea.io/en-us/), [Miniflux](https://miniflux.app/), [Netdata](https://my-netdata.io/), [Nextcloud](https://nextcloud.com/), [Plex](https://www.plex.tv/), [Tautulli](http://tautulli.com/) and [ZNC](https://wiki.znc.in/ZNC)!

If (like I was) you're using FreeNAS and getting frustrated with the high levels of complexity for a simple home server, or you want to build your own home server solution, then take a look at [Ansible-NAS](https://github.com/davestephens/ansible-nas) and see what you think.