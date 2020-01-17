FROM node:11-alpine

RUN npm i -g github-release-notes

RUN apk update && \
    apk add --no-cache git openssh

USER node

ENV PATH $PATH:/usr/local/bin

ENTRYPOINT ["gren"]
