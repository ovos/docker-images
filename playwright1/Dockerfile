FROM mcr.microsoft.com/playwright:v1.49.1-noble

USER root

RUN apt-get update \
    && apt-get install --yes wget curl nginx default-mysql-client lftp \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

ENV DOCKERIZE_VERSION=v0.20.2
RUN mkdir -p /usr/local/bin/ \
	&& wget https://github.com/powerman/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m | tr '[:upper:]' '[:lower:]') -O /usr/local/bin/dockerize \
	&& chmod +x /usr/local/bin/dockerize

RUN mkdir /home/circleci
