FROM node:14-alpine

RUN apk update && \
    apk add --no-cache git openssh bash && \
    addgroup -S circleci && adduser -S circleci -G circleci

ENV SENTRY_DNS https://github.com/getsentry/sentry-cli/releases/download/
RUN npm i -g @sentry/cli --sentrycli_cdnurl=${SENTRY_DNS} --unsafe-perm

ENV PATH $PATH:/usr/local/bin

USER circleci

ENTRYPOINT ["sentry-cli"]
