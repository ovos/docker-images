FROM powerman/dockerize:0.24.0 AS dockerize

FROM node:22-bookworm

RUN apt-get update \
    && apt-get install --yes wget curl nginx default-mysql-client lftp \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN npx -y playwright@${PLAYWRIGHT_VERSION:-1.62.1} install --with-deps

COPY --from=dockerize /usr/local/bin/dockerize /usr/local/bin/

RUN mkdir /home/circleci
