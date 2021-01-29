FROM circleci/node:14

USER root

ENV DOCKERIZE_VERSION=v0.13.1
RUN mkdir -p /usr/local/bin/ \
	&& wget https://github.com/powerman/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m | tr '[:upper:]' '[:lower:]') -O /usr/local/bin/dockerize \
	&& chmod +x /usr/local/bin/dockerize

USER circleci

