Dockrsync
=========

Dockrsync is a tool that will rsync changes to files from your project directory
to a docker container.

This allows you to do local development on MacOS without the read performance
issues of shared filesystems (such as vboxsf, osxfs, and NFS) that slow down
interpretation and compilation.

Additionally it will allow local development against a remote docker engine from
MacOS and Linux, as long as your docker client is configured to connect to the
remote docker-engine.

Prerequisites
-------------

* Docker - (Docker for Mac, docker-machine or docker in Linux)
* docker-compose - Comes with most Docker installations
* rsync - v2.6 is available on MacOS, though v3.1+ is recommended, `brew install rsync`
* fswatch - `brew install fswatch`

The Docker containers will need to have rsync installed within them.

Download
--------

```bash
curl -o /usr/local/bin/dockrsync https://raw.githubusercontent.com/webtatic/dockrsync/master/dockrsync
chmod +x /usr/local/bin/dockrsync
```

Usage
-----

Set up the default configuration for a project:

```bash
dockrsync setup
```

Push changes up to the docker container:

```bash
dockrsync push
```

Watch for changes in files and sync those that change:

```bash
dockrsync watch
```

License
-------

MIT

Copyright
---------
Copyright (c) 2017 Andy Thompson

Based on a Bash tool called cp-remote Copyright (c) 2016 Inviqa UK Limited
