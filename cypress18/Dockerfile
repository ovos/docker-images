FROM powerman/dockerize:0.24.0 AS dockerize

FROM cypress/base:18.12.1

USER root

RUN apt-get update && apt-get upgrade -y \
    && apt-get install --yes wget curl nginx default-mysql-client lftp \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

COPY --from=dockerize /usr/local/bin/dockerize /usr/local/bin/

RUN mkdir /home/circleci
