dock0/webapp
=======

[![Automated Build](http://img.shields.io/badge/automated-build-green.svg)](https://hub.docker.com/r/dock0/amylum/)
[![MIT Licensed](http://img.shields.io/badge/license-MIT-green.svg)](https://tldrlegal.com/license/mit-license)

Container based on [dock0/foreman](https://github.com/dock0/foreman) that adds nginx as a reverse proxy to a webapp

## Usage

This is designed to be used as a building block for webapps. Create a Dockerfile like the following:

```
FROM dock0/webapp
MAINTAINER akerl <me@lesaker.org>
RUN pacman -S --noconfirm --needed base-devel
ADD source /srv/app
RUN bundle install --gemfile /srv/app/Gemfile
```

Your app should listen on localhost:8080 for HTTP connections proxied from nginx.

If you want to accept HTTPS connections, provide /opt/ssl/cert and /opt/ssl/key via a volume.

## License

This repo is released under the MIT License. See the bundled LICENSE file for details.

