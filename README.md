# Supported tags and respective `Dockerfile` links

-	[`9.1.6`, `latest` (*Dockerfile*)](https://github.com/sashgorokhov/docker-teamcity/blob/master/Dockerfile)

[![](https://images.microbadger.com/badges/image/sashgorokhov/teamcity.svg)](http://microbadger.com/images/sashgorokhov/teamcity "Get your own image badge on microbadger.com")

# TeamCity

TeamCity is a Java-based build management and continuous integration server from JetBrains.

> [https://en.wikipedia.org/wiki/TeamCity](https://en.wikipedia.org/wiki/TeamCity)

![logo](http://blog.jetbrains.com/wp-content/uploads/2014/03/logo_teamcity.jpg)

# How to use this image

```console
$ docker run --name teamcity -p 8111:8111 -d sashgorokhov/teamcity
```

This will start a Teamcity server listening on the default port of 8111.
Wait a couple of minutes, teamcity is rather heavy machine and needs some time to startup.
Then access it via `http://localhost:8111` or `http://host-ip:8111` in a browser.
Image's supported volumes:
- `/mnt/teamcity` - teamcity's data directory

```console
$ docker run --name teamcity -p 8111:8111 -d -v /mnt/teamcity:/mnt/teamcity  sashgorokhov/teamcity
```

To start teamcity agents, you can use [teamcity agent docker image](https://hub.docker.com/r/sashgorokhov/teamcity-agent). 


# Using with PostgreSQL external database
<b>Only 9.4 version is supported.</b>

Example compose file: [compose file](https://github.com/sashgorokhov/docker-teamcity/blob/master/docker-compose-postgres.yml)

Simply specify environment variable `DATABASE=POSTGRES` (Uppercase only), and script will download approtiate driver for teamcity on server startup.


# Supported Docker versions

This image is officially supported on Docker version 1.10.2.
Support for older versions (down to 1.6) is provided on a best-effort basis.
Please see [the Docker installation documentation](https://docs.docker.com/installation/) for details on how to upgrade your Docker daemon.
