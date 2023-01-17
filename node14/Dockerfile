FROM cimg/node:14.21

USER root

RUN apt-get update \
    && apt-get install --yes wget nginx \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

COPY nginx.conf /etc/nginx/nginx.conf

RUN chown -R circleci:circleci /etc/nginx /var/log/nginx \
    && rm -rf /etc/nginx/sites-enabled/* \
    && rm -rf /etc/nginx/sites-available/*

ENV DOCKERIZE_VERSION=v0.16.0
RUN mkdir -p /usr/local/bin/ \
	&& wget https://github.com/powerman/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m | tr '[:upper:]' '[:lower:]') -O /usr/local/bin/dockerize \
	&& chmod +x /usr/local/bin/dockerize

RUN npm install -g madge

USER circleci

