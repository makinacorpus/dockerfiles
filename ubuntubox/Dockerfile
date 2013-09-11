FROM ubuntu:12.04
MAINTAINER Makina Corpus "python@makina-corpus.org"

#
#  Universe + Upgrade
#...
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get -qq update
RUN apt-get upgrade -y

#
#  Tools
#...
RUN apt-get install -y python-software-properties openssh-server wget curl build-essential bzip2 unzip gettext
RUN apt-add-repository -y ppa:git-core/ppa
RUN apt-get -qq update
RUN apt-get install -y git-core

#
#  Locales
#...
RUN apt-get install -y language-pack-en language-pack-fr
ENV LANGUAGE en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8
RUN locale-gen en_US.UTF-8
RUN locale-gen fr_FR.UTF-8
RUN dpkg-reconfigure locales
