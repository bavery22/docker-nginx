# About this Repo

This is the Git repo of the official Docker image for [nginx](https://registry.hub.docker.com/_/nginx/). See the
Hub page for the full readme on how to use the Docker image and for information
regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs),
specifically in [docker-library/docs/nginx](https://github.com/docker-library/docs/tree/master/nginx).


## This is a docker image derived from the above.  It has a couple of additions:

 * It enables an additional location with auto indexing aka directory browsing turned on: /usr/share/nginx/sstate
 * Only the stable/buster-perl dockerfile is supported.

### To Run/Use
This is based on https://wiki.yoctoproject.org/wiki/TipsAndTricks/TeamWorkflows .
 * Have your sstate you want to serve up somwhere like /bigdir/sstate-cache-all
 * Run this container and bind mount that dir in:
 ** $ docker run --name sstate-nginx -p 8080:80  -v /bigdir/sstate-cache-all:/usr/share/nginx/sstate:ro -d --rm bavery/state-nginx
 * To see error logs from nginx:
 ** $ docker logs sstate-nginx
