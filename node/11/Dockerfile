FROM circleci/node:11

MAINTAINER mkr@ovos.at

ENV DOCKERIZE_VERSION=v0.11.2

USER root

RUN mkdir -p /usr/local/bin/ \
	&& wget https://github.com/powerman/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m | tr '[:upper:]' '[:lower:]') -O /usr/local/bin/dockerize \
	&& chmod +x /usr/local/bin/dockerize

RUN apt-get update \
	&& apt-get install -y \
	jq lftp nginx-light \
	# cypress depdendencies \
	libgtk2.0-0 libgtk-3-0 libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2 libxtst6 xauth xvfb \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

ENV PATH=$PATH:/usr/local/bin

USER circleci
