FROM node:14-alpine

RUN apk update && \
    apk add --no-cache git openssh bash && \
    addgroup -S circleci && adduser -S circleci -G circleci

RUN npm i -g github-release-notes

ENV PATH $PATH:/usr/local/bin

USER circleci

ENTRYPOINT ["gren"]
