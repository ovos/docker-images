FROM powerman/dockerize:0.24.0 AS dockerize

FROM cimg/node:20.19

USER root

RUN apt-get update \
    && apt-get install --yes wget nginx \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

COPY nginx.conf /etc/nginx/nginx.conf

RUN chown -R circleci:circleci /etc/nginx /var/log/nginx \
    && rm -rf /etc/nginx/sites-enabled/* \
    && rm -rf /etc/nginx/sites-available/*

COPY --from=dockerize /usr/local/bin/dockerize /usr/local/bin/

RUN npm install -g madge@6.1.0

USER circleci

