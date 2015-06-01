# dockerhub - A repository for various dockerfiles
# For more information; http://github.com/cmfatih/dockerhub
#
# phantomjs
#
# Usage
#   sudo docker run fentas/phantomjs /usr/bin/phantomjs -v
#   sudo docker run fentas/phantomjs /usr/bin/casperjs --version
#   sudo docker run -v `pwd`:/mnt/test fentas/phantomjs /usr/bin/phantomjs /mnt/test/test.js

# VERSION 1.0.1

FROM ubuntu:12.04

MAINTAINER fentas <jan.guth.so>

# Env
ENV PHANTOMJS_VERSION 2.0.0
ENV CASPERJS_VERSION_T master

# Commands
RUN \
  apt-get update && \
  apt-get upgrade -y && \
  apt-get install -y vim git wget libfreetype6 libfontconfig bzip2 unzip && \
  mkdir -p /srv/var && \
  wget -q --no-check-certificate -O /tmp/phantomjs-$PHANTOMJS_VERSION-source.zip https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-$PHANTOMJS_VERSION-source.zip && \
  unzip /tmp/phantomjs-$PHANTOMJS_VERSION-source.zip -d /tmp && \
  rm -f /tmp/phantomjs-$PHANTOMJS_VERSION-source.zip  && \
  cd /tmp/phantomjs-$PHANTOMJS_VERSION-source/ && \
  ./configure && make && sudo make install && \
  cd / && rm -R /tmp/phantomjs-$PHANTOMJS_VERSION-source/ && \
  git clone https://github.com/n1k0/casperjs.git /srv/var/casperjs && \
  cd /srv/var/casperjs && \
  git checkout $CASPERJS_VERSION_T && \
  ln -s /srv/var/casperjs/bin/casperjs /usr/bin/casperjs && \
  apt-get autoremove -y && \
  apt-get clean all

# Default command
ENTRYPOINT "phantomjs"
CMD ["--help"]
