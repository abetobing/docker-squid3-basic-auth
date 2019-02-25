# squid3-basic-ncsa-auth-docker

A Squid3 caching proxy with SSL enabled in a Docker container, based on
https://github.com/toffer/docker-squid3-ssl and meant to be used from within
other Docker containers.

## Details

* ubuntu:bionic-20181204
* Squid (Version 3.5.27).

## Usage

Start Squid3 setting its hostname and container name:

```
$ docker run --name squid3-with-basic-auth -d --restart=always \
    --publish 8888:8888 \
    --volume /opt/var/log/squid3:/var/log/squid3 \
    --volume /opt/etc/squid3/squid.conf:/etc/squid3/squid.conf abetobing/docker-squid3-basic-auth:latest
```


## Parameter

Basic authentication user and password, default is proxy:secret.
* SQUID_AUTH_USER = proxy 
* SQUID_AUTH_PASSWORD = secret
